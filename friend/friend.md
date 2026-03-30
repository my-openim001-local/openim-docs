# Friend/Contact management route

## 1. Friend management with rest api

Request url exp: `${imServerUrl}/friend/get_friend_list`

- Url: IM-Server
- Headers:
  - token: im-server token
  - operationID: unique string

### Friend Management

- POST /get_friend_list — paginated full list, [ref](https://docs.openim.io/restapi/apis/friendsManagement/getFriendList)
- POST /get_designated_friends — fetch specific friends by ID, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L100),
  [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L104C9-L104C33)
- POST /get_specified_friends_info — detailed profile info for specific friends, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L198),
  [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L203)
- POST /set_friend_remark — set/update a friend's alias, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L173), [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L178)
- POST /delete_friend — remove a friend, [ref](https://docs.openim.io/restapi/apis/friendsManagement/deleteFriend)
- POST /import_friend — bulk import friends
- POST /update_friends — update friend metadata, [ref](https://docs.openim.io/restapi/apis/friendsManagement/updateFriends)
- POST /is_friend — check if two users are friends [ref](https://docs.openim.io/restapi/apis/friendsManagement/checkFriend)
- POST /get_friend_id — look up friend IDs, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L190),
  [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L194)

### Apply / Respond

- POST /add_friend — send a friend request, [ref](https://docs.openim.io/restapi/apis/friendsManagement/sendApplication)
- POST /add_friend_response — accept or reject a request [ref](https://docs.openim.io/restapi/apis/friendsManagement/processApplication)
- POST /get_friend_apply_list — incoming requests (received) [ref](https://docs.openim.io/restapi/apis/friendsManagement/getRecvApplication)
- POST /get_self_friend_apply_list — outgoing requests (sent) [ref](https://docs.openim.io/restapi/apis/friendsManagement/getSentApplication)
- POST /get_designated_friend_apply — request status for a specific user, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L56),
  [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L61)
- POST /get_self_unhandled_apply_count — count of pending incoming requests, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L65),
  [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L70)

### Black List

- POST /add_black — block a user, [ref](https://docs.openim.io/restapi/apis/friendsManagement/addBlackList)
- POST /remove_black — unblock a user, [ref](https://docs.openim.io/restapi/apis/friendsManagement/deleteBlackList)
- POST /get_black_list — paginated list of blocked users, [ref](https://docs.openim.io/restapi/apis/friendsManagement/getBlackList)
- POST /get_specified_blacks — fetch specific blocked users, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L243),
  [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L248)
- POST /get_incremental_blacks — delta sync for blocked users, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L248),
  [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L234)

### Sync / Util

- POST /get_incremental_friends — delta sync, only changed friends since last sequence, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L213),
  [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L219)
- POST /get_full_friend_user_ids — full list of friend user IDs for client reconciliation, [req data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L253),
  [resp data](https://github.com/openimsdk/protocol/blob/main/relation/relation.proto#L258)

## 2. Friend management, listen sockets event

See socket example [here](https://docs.openim.io/sdks/listener/friendshipListener)
