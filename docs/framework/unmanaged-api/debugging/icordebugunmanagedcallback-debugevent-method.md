---
title: ICorDebugUnmanagedCallback::DebugEvent-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: beb2b9f17696e293d14cf997ef69deb7557ed0bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479243"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>ICorDebugUnmanagedCallback::DebugEvent-Methode
Benachrichtigt den Debugger, dass ein systemeigenes Ereignis ausgelöst wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pDebugEvent`  
 [in] Ein Zeiger auf das systemeigene-Ereignis.  
  
 `fOutOfBand`  
 [in] `true`, wenn die Interaktion mit dem verwalteten Prozesszustand nicht möglich ist, nachdem ein nicht verwaltetes Ereignis, bis der Debugger ruft auftritt [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Ist der im Debugmodus befindlichen Thread ein Win32-Thread, verwenden Sie keine Member des Win32-Schnittstelle zu debuggen. Rufen Sie `ICorDebugController::Continue` nur in einem Win32-Thread und nur, wenn nach einem Out-of-Band-Ereignis fortfahren.  
  
 Die `DebugEvent` Rückruf befolgt nicht die Standardregeln für Rückrufe. Beim Aufruf `DebugEvent`, der Prozess werden in den unformatierten, Betriebssystem-Debug-Zustand "beendet". Der Prozess wird nicht synchronisiert werden. Er wechselt automatisch in den Status "synchronisiert" bei Bedarf, um Anforderungen für Informationen zu verwaltetem Code zu erfüllen, durch die in anderen geschachtelten möglicherweise `DebugEvent` Rückrufe.  
  
 Rufen Sie [ICorDebugProcess:: ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) für den Prozess, um ein Ausnahmeereignis vor dem Fortsetzen des Prozesses zu ignorieren. Das Aufrufen dieser Methode sendet DBG_CONTINUE anstatt DBG_EXCEPTION_NOT_HANDLED in der Anforderung weiter und automatisch löscht Out-of-Band-Haltepunkte und Ausnahmen von einem Schritt. Out-of-Band-Ereignisse können zu jedem Zeitpunkt stammen, selbst wenn die Anwendung im Debugmodus befindlichen beendet wird und wenn bereits eine ausstehende in-Band-Ereignis.  
  
 In .NET Framework, Version 2.0 sollte der Debugger sofort nach einem Haltepunktereignis für die Out-of-Band-fortfahren. Der Debugger verwendet werden soll die [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) und [ICorDebugProcess2:: ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) Methoden zum Hinzufügen und Entfernen von Haltepunkten. Diese Methoden werden über die Out-of-Band-Haltepunkte automatisch übersprungen. Daher muss die einzigen Out-of-Band-Haltepunkte, die weitergeleitet werden unformatierte Haltepunkte, die bereits im Anweisungsstream, z. B. durch einen Aufruf der Win32- `DebugBreak` Funktion. Versuchen Sie nicht mit `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), sowie alle anderen Mitglieder der [Debug-API](../../../../docs/framework/unmanaged-api/debugging/index.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugUnmanagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
