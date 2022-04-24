** Go in es_extended in config.lua and insert Visum and Minuten**
```LUA
Config.Accounts = {
    bank = _U('account_bank'),
    black_money = _U('account_black_money'),
    money = _U('account_money'),
    Visum = 'Visum',
    Minuten = 'Minuten'
}
```
** Go in es_extended in main.lua and insert this**
```LUA
CreateThread(function()
    while true do
        Wait(15 * 60000)
        for _, xPlayer in pairs(ESX.GetExtendedPlayers()) do
            xPlayer.addAccountMoney('Visum', 1)
            xPlayer.addAccountMoney('Minuten', 15)
        end
    end
end)
```

** Get Minuten and Visum**
```LUA
local Visum = xPlayer.getAccount('Visum').money
local Minuten = xPlayer.getAccount('Minuten').money

print("You have"..Minuten.." minutes on this Server")
print("You Visum is "..Visum)

```
