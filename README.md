# Quest-Seatbelt-Script-QBCORE
Simple seatbelt scripts with flashing indicator and noise, used to enhance your Roleplay!

# How to Install
Place the quest-seatbelt folder in your server's resources folder.

Add start quest-seatbelt to your server.cfg file to ensure the script is started when your server starts up.

Open your server.lua file located in your resources\qb-core\server folder.

Add the following code to the top of your server.lua file:
`QBCore = nil
TriggerEvent('QBCore:GetObject', function(obj) QBCore = obj end)`
This code will ensure that the QBCore object is available for use in the script.

Add the following code to the bottom of your server.lua file:
`QBCore.Functions.CreateCallback('seatbelt:GetSeatbeltStatus', function(source, cb)
    local xPlayer = QBCore.Functions.GetPlayer(source)
    local seatbeltStatus = xPlayer.get('seatbelt')
    cb(seatbeltStatus)
end)

QBCore.Functions.CreateCallback('seatbelt:SetSeatbeltStatus', function(source, cb, status)
    local xPlayer = QBCore.Functions.GetPlayer(source)
    xPlayer.set('seatbelt', status)
    cb(true)
end)`
This code will create two server-side callbacks that will allow the client-side script to retrieve and set the player's seatbelt status.

# Support
If you require feel free to join our [Discord](https://discord.gg/BsMPHWmXuM).

# Credits
Dusty#7244 - Developer Of This Project.

zesty#6969 - Lead Developer - [Quest](https://discord.gg/BsMPHWmXuM)
