# Request Identifier and map struct name

All struct available at [openim protocol repository](https://github.com/openimsdk/protocol) or [Our chat team repo](https://github.com/MetaElevenPhnomPenh/protocol)

format folder.structName, exp: sdkws.GetMaxSeqReq

1. GetMaxSeqResp
   - ReqIdentifier: 1001
   - request struct [sdkws.GetMaxSeqReq](https://github.com/openimsdk/protocol/blob/main/sdkws/sdkws.proto#L161)
   - response struct [sdkws.GetMaxSeqResp](https://github.com/openimsdk/protocol/blob/main/sdkws/sdkws.proto#L165)

2. PullMsgBySeqList
   - ReqIdentifier: 1002
   - request struct [msg.GetSeqMessageReq](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L333)
   - response struct [msg.GetSeqMessageResp](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L339)

3. SendMsg
   - ReqIdentifier: 1003
   - request struct [sdkws.MsgData](https://github.com/openimsdk/protocol/blob/main/sdkws/sdkws.proto#L176)
   - response struct [msg.SendMsgResp](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L41)

4. SendSignalMsg
   - ReqIdentifier: 1004
   - request struct [msg.SendMsgReq](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L37)
   - response struct[msg.SendMsgResp](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L41)

5. PullMsg
   - ReqIdentifier: 1005
   - request struct [msg.GetSeqMessageReq](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L333)
   - response struct [msg.GetSeqMessageResp](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L339)

6. GetConvMaxReadSeq
   - ReqIdentifier: 1006
   - request struct [msg.GetConversationsHasReadAndMaxSeqReq](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L188)
   - response struct [msg.GetConversationsHasReadAndMaxSeqResp](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L200)

7. PullConvLastMessage
   - ReqIdentifier 1007
   - request struct [msg.GetLastMessageReq](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L382)
   - response struct [msg.GetLastMessageResp](https://github.com/openimsdk/protocol/blob/main/msg/msg.proto#L386)

8. PushMsg
   - ReqIdentifier 2001
   - response struct [sdkws.PushMessages](https://github.com/openimsdk/protocol/blob/main/sdkws/sdkws.proto#L200)

9. KickOnlineMsg
   - ReqIdentifier 2002
   * no struct

10. LogoutMsg
    - ReqIdentifier 2003
    - request struct [push.DelUserPushTokenReq](https://github.com/openimsdk/protocol/blob/main/push/push.proto#L16)
    - response struct [push.DelUserPushTokenResp](https://github.com/openimsdk/protocol/blob/main/push/push.proto#L21C9-L21C29)

11. WsSetBackgroundStatus

- ReqIdentifier 2004
- request struct [sdkws.SetAppBackgroundStatusReq](https://github.com/openimsdk/protocol/blob/main/sdkws/sdkws.proto#L554)
- response nil

12. SubUserOnlineStatus

- ReqIdentifier 2005
- request struct [sdkws.SubUserOnlineStatus](https://github.com/openimsdk/protocol/blob/main/sdkws/sdkws.proto#L588)
- response struct [sdkws.SubUserOnlineStatusTips](https://github.com/openimsdk/protocol/blob/main/sdkws/sdkws.proto#L584)
