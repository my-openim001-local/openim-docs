# Request Identifier and map struct name

All struct available at `https://github.com/MetaElevenPhnomPenh/protocol`

format folder.structName, exp: sdkws.GetMaxSeqReq

1. GetMaxSeqResp
   - ReqIdentifier: 1001
   - request struct sdkws.GetMaxSeqReq
   - response struct sdkws.GetMaxSeqResp

2. PullMsgBySeqList
   - ReqIdentifier: 1002
   - request struct msg.GetSeqMessageReq
   - response struct msg.GetSeqMessageResp

3. SendMsg
   - ReqIdentifier: 1003
   - request struct sdkws.MsgData
   - response struct msg.SendMsgResp

4. SendSignalMsg
   - ReqIdentifier: 1004
   - request struct msg.SendMsgReq
   - response struct msg.SendMsgResp

5. PullMsg
   - ReqIdentifier: 1005
   - request struct msg.GetSeqMessageReq
   - response struct msg.GetSeqMessageResp,

6. GetConvMaxReadSeq
   - ReqIdentifier: 1006
   - request struct msg.GetConversationsHasReadAndMaxSeqReq
   - response struct msg.GetConversationsHasReadAndMaxSeqResp

7. PullConvLastMessage
   - ReqIdentifier 1007
   - request struct msg.GetLastMessageReq
   - response struct msg.GetLastMessageResp

8. PushMsg
   - ReqIdentifier 2001
   - response struct sdkws.PushMessages

9. KickOnlineMsg
   - ReqIdentifier 2002
   * no struct

10. LogoutMsg
    - ReqIdentifier 2003
    - request struct push.DelUserPushTokenReq
    - response struct push.DelUserPushTokenResp

11. WsSetBackgroundStatus

- ReqIdentifier 2004
- request struct sdkws.SetAppBackgroundStatusReq
- response nil

12. SubUserOnlineStatus

- ReqIdentifier 2005
- request struct sdkws.SubUserOnlineStatus
- response struct sdkws.SubUserOnlineStatusTips
