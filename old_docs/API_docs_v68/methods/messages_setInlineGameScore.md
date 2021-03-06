---
title: messages.setInlineGameScore
description: messages.setInlineGameScore parameters, return type and example
---
## Method: messages.setInlineGameScore  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|edit\_message|[Bool](../types/Bool.md) | Optional|
|force|[Bool](../types/Bool.md) | Optional|
|id|[InputBotInlineMessageID](../types/InputBotInlineMessageID.md) | Yes|
|user\_id|[InputUser](../types/InputUser.md) | Yes|
|score|[int](../types/int.md) | Yes|


### Return type: [Bool](../types/Bool.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $MadelineProto->bot_login($token);
}
if (isset($number)) { // Login as a user
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$Bool = $MadelineProto->messages->setInlineGameScore(['edit_message' => Bool, 'force' => Bool, 'id' => InputBotInlineMessageID, 'user_id' => InputUser, 'score' => int, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - messages.setInlineGameScore
* params - `{"edit_message": Bool, "force": Bool, "id": InputBotInlineMessageID, "user_id": InputUser, "score": int, }`



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/messages.setInlineGameScore`

Parameters:

edit_message - Json encoded Bool

force - Json encoded Bool

id - Json encoded InputBotInlineMessageID

user_id - Json encoded InputUser

score - Json encoded int




Or, if you're into Lua:

```
Bool = messages.setInlineGameScore({edit_message=Bool, force=Bool, id=InputBotInlineMessageID, user_id=InputUser, score=int, })
```

