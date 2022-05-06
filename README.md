
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Ui = Library.CreateLib("Kaz Hub", "Ocean")

local Tab1 = Ui:NewTab("Main")

local Tab2 = Ui:NewTab("Farm")

local Tab3 = Ui:NewTab("Players")

local Tab4 = Ui:NewTab("Auto Egg")

local Tab5 = Ui:NewTab("Auto Boss")

local Tab6 = Ui:NewTab("Teleport")

local Section1 = Tab2:NewSection("Auto Farm")

local Section2 = Tab2:NewSection("Auto Rebirths")

local Section3 = Tab4:NewSection("Auto Egg Map 1")

local Section4 = Tab5:NewSection("Map 1")

local Section5 = Tab6:NewSection("Map")

-- Teleport
-- Anime Village
Section5:NewButton("Anime Village", "", function()
    game:service'ReplicatedStorage'.Remotes.RequestTeleport:InvokeServer("world", "Anime Village")
    print("Clicked")
end)
    --Pirate Docks
    Section5:NewButton("Pirate Docks", "", function ()
    game:service'ReplicatedStorage'.Remotes.RequestTeleport:InvokeServer("world", "Pirate Docks")
    print("Clicker")
    end)
    -- Purple Forest
    Section5:NewButton("Purple Forest", "", function ()
        game:service'ReplicatedStorage'.Remotes.RequestTeleport:InvokeServer("world", "Purple Forest")
        print("Clicker")
    end)
    -- Shinobi Village
    Section5:NewButton("Shinobi Village", "", function ()
        game:service'ReplicatedStorage'.Remotes.RequestTeleport:InvokeServer("world", "Shinobi Village")
        print("Clicker")
    end)
--Auto Boss
Section4:NewToggle("Evil Vegete", "", function (Boss)
    getgenv().BossA = true
    if Boss == true then
        while getgenv().BossA == true do
            wait()
            game:service'ReplicatedStorage'.Remotes.RequestTeleport:InvokeServer("world", "Anime Village")
            local nguoichoi = game.Players.LocalPlayer.Character.HumanoidRootPart
local humanoid = game.Players.LocalPlayer.Character.Humanoid

humanoid:ChangeState(Enum.HumanoidStateType.Running)

nguoichoi.CFrame = CFrame.new(110, 21.2, 740)

            game:service'ReplicatedStorage'.Remotes.ClickRemote:FireServer(false, false, "Clicker!", "Evil Vegete")
        end
    else
        getgenv().BossA = false
    end
end)

--Auto Farm
Section1:NewToggle("Auto Farm", "Not Things", function(Click)
    getgenv().AutoClicker = true
    if Click == true then
        while getgenv().AutoClicker == true do -- true thì nó auto làm đến khi tắt
            wait()
            game:service'ReplicatedStorage'.Remotes.ClickRemote:FireServer(false, false, "Clicker!")
        end
    else
        getgenv().AutoClicker = false -- false tắt rồi thì tắt ko auto nữa
    end 
end)

-- Auto Rebirths
Section2:NewToggle("Auto Rebirths", "Not Things", function(Rebirths)
    getgenv().AutoRebirths = true
    if Rebirths == true then
        while getgenv().AutoRebirths == true do
        wait()
            game:service'ReplicatedStorage'.Remotes.RebirthRemote:FireServer(771)
        end
    else
     getgenv().AutoRebirths = false
    end 
    end)
    --Auto Egg
    --Map 1
    Section3:NewToggle("Dragon Star", "500 Clicks", function(Map1a)
        getgenv().Egg1a = true
        if Map1a == true then
            while getgenv().Egg1a == true do
            wait()
            game:service'ReplicatedStorage'.Remotes.RequestTeleport:InvokeServer("world", "Anime Village")
            local nguoichoi = game.Players.LocalPlayer.Character.HumanoidRootPart
            local humanoid = game.Players.LocalPlayer.Character.Humanoid

            humanoid:ChangeState(Enum.HumanoidStateType.Running)

            nguoichoi.CFrame = CFrame.new(331, 1.22, 501)
            game:service'ReplicatedStorage'.Remotes.OpenEgg:InvokeServer("Dragon Star", false, false)
            end
        else
            getgenv().Egg1a = false
        end
    end)
    Section3:NewToggle("Demon Star", "50k Clicks", function(Map1)
        getgenv().Egg1 = true
        if Map1 == true then 
            while getgenv().Egg1 == true do
            wait()
            game:service'ReplicatedStorage'.Remotes.RequestTeleport:InvokeServer("world", "Anime Village")
            local nguoichoi = game.Players.LocalPlayer.Character.HumanoidRootPart
            local humanoid = game.Players.LocalPlayer.Character.Humanoid

            humanoid:ChangeState(Enum.HumanoidStateType.Running)

            nguoichoi.CFrame = CFrame.new(331, 1.09, 516)
            game:service'ReplicatedStorage'.Remotes.OpenEgg:InvokeServer("Demon Star", false, false)
            end
        else
            getgenv().Egg1 = false
        end
    end)
--Map 2

