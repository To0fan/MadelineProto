---
title: account.changePhone
description: account.changePhone parameters, return type and example
---
## Method: account.changePhone  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|phone\_number|[string](../types/string.md) | Yes|
|phone\_code\_hash|[string](../types/string.md) | Yes|
|phone\_code|[string](../types/string.md) | Yes|


### Return type: [User](../types/User.md)

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

$User = $MadelineProto->account->changePhone(['phone_number' => 'string', 'phone_code_hash' => 'string', 'phone_code' => 'string', ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - account.changePhone
* params - `{"phone_number": "string", "phone_code_hash": "string", "phone_code": "string", }`



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/account.changePhone`

Parameters:

phone_number - Json encoded string

phone_code_hash - Json encoded string

phone_code - Json encoded string




Or, if you're into Lua:

```
User = account.changePhone({phone_number='string', phone_code_hash='string', phone_code='string', })
```

