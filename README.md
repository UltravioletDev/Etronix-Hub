local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Etronix Hub", "BloodTheme")
local StealthMode = true -- If game has an anticheat that checks the logs

local Indicator

--MAIN--
local Tab = Window:NewTab("Main")
local Section = Tab:NewSection("Anti (RECOMMENDED)")
Section:NewToggle("AntiCheat Bypass", "Bypasses/stops the AntiCheat", function(state)
    if state then
        print("AntiCheat Bypass Enabled")
        loadstring(game:HttpGet("https://raw.githubusercontent.com/luckywastakenwow/roblox-jp-script/main/anti%20bypass%201"))()
    else
        print("AntiCheat Bypass Disabled")
    end
end)
Section:NewToggle("AntiCheat Bypass 2", "Hooks the AntiCheat", function(state)
    if state then
        print("AntiCheat Bypass 2 Enabled")
        loadstring(game:HttpGet("https://raw.githubusercontent.com/luckywastakenwow/roblox-jp-script/main/anti%20bypass%202"))()
    else
        print("AntiCheat Bypass 2 Disabled")
    end
end)
Section:NewToggle("AntiCheat Bypass 3", "Speed AntiCheat Bypass", function(state)
    if state then
        print("AntiCheat Bypass 3 Enabled")
        loadstring(game:HttpGet("https://raw.githubusercontent.com/luckywastakenwow/roblox-jp-script/main/anti%20bypass%203"))
    else
        print("AntiCheat Bypass 3 Disabled")
    end
end)
Section:NewToggle("AntiKick", "Stops you from getting kicked", function(state)
    if state then
        print("AntiKick Enabled")
        loadstring(game:HttpGet("https://raw.githubusercontent.com/luckywastakenwow/roblox-jp-script/main/antikick"))()
    else
        print("AntiKick Disabled")
    end
end)
Section:NewToggle("AntiKick 2", "Extra protection for AntiKick", function(state)
    if state then
        print("AntiKick 2 Enabled")
        loadstring(game:HttpGet("https://raw.githubusercontent.com/luckywastakenwow/roblox-jp-script/main/antikick%202"))()
    else
        print("AntiKick 2 Disabled")
    end
end)
Section:NewToggle("AntiMultiple", "Anti-Crash, Anti-Fling, Anti-Freeze, Anti-Punish", function(state)
    if state then
        print("AntiMultiple Enabled")
        loadstring(game:HttpGet("https://raw.githubusercontent.com/luckywastakenwow/roblox-jp-script/main/antimultiple"))()
    else
        print("AntiMultiple Disabled")
    end
end)
local Section = Tab:NewSection("Anti-Steal/Anti-Logger (RECOMMENDED)")
Section:NewButton("Anti-Steal/Anti-Logger", "Stops chat logging", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/luckywastakenwow/anti-logger/main/anti-logger%20v8", true))()
end)
local Section = Tab:NewSection("AimAssist")
Section:NewToggle("AimAssist", "Like AimBot, it aims at your enemy", function(state)
    if state then
        print("AimAssist Enabled")
    else
        print("AimAssist Disabled")
end
end)
Section:NewDropdown("Aimpart", "DropdownInf", {"Head", "Torso", "Left Leg", "Right Leg", "Left Arm", "Right Arm"}, function(currentOption)
    print(currentOption)
end)
local Section = Tab:NewSection("God Mode")
Section:NewToggle("God Mode", "Gives you inf health, but may kick you", function(state)
    if state then
        print("God Mode Enabled")
        game.Players.LocalPlayer.Character.Humanoid:Remove()
Instance.new('Humanoid', game.Players.LocalPlayer.Character)
game:GetService("Workspace")[game.Players.LocalPlayer.Name]:FindFirstChildOfClass(
'Humanoid').HipHeight = 2
    else
        print("God Mode Disabled")
    end
end)
local Section = Tab:NewSection("Noclip")
Section:NewToggle("Noclip",  "Walk through walls", function(state)
    if state then
        print("Noclip Enabled")
        local StealthMode = true -- If game has an anticheat that checks the logs

local Indicator

if not StealthMode then
    local ScreenGui = Instance.new("ScreenGui", game.CoreGui)
    print("NOCLIP: Press E to Activate")
    Indicator = Instance.new("TextLabel", ScreenGui)
    Indicator.AnchorPoint = Vector2.new(0, 1)
    Indicator.Position = UDim2.new(0, 0, 1, 0)
    Indicator.Size = UDim2.new(0, 200, 0, 50)
    Indicator.BackgroundTransparency = 1
    Indicator.TextScaled = true
    Indicator.TextStrokeTransparency = 0
    Indicator.TextColor3 = Color3.new(0, 0, 0)
    Indicator.TextStrokeColor3 = Color3.new(1, 1, 1)
    Indicator.Text = "Noclip: Enabled"
end

local noclip = false
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

local mouse = player:GetMouse()

mouse.KeyDown:Connect(function(key)
    if key == "e" then
        noclip = not noclip

        if not StealthMode then
            Indicator.Text = "Noclip: " .. (noclip and "Enabled" or "Disabled")
        end
    end
end)

while true do
    player = game.Players.LocalPlayer
    character = player.Character

    if noclip then
        for _, v in pairs(character:GetDescendants()) do
            pcall(function()
                if v:IsA("BasePart") then
                    v.CanCollide = false
                end
            end)
        end
    end

    game:GetService("RunService").Stepped:wait()
end
end
end)

--LOCAL PLAYER--
local Tab = Window:NewTab("Local Player")
local Section = Tab:NewSection("Local Player")
Section:NewSlider("Walk Speed", "Makes you faster or slower", 500, 16, function(s)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)
Section:NewSlider("Jump Power", "Modifies how high or low you can jump", 500, 55, function(p) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = p
end)
Section:NewButton("InfJump", "Jump In The Air", function()
    print("InfJump Enabled")
    local InfiniteJumpEnabled = true
    game:GetService("UserInputService").JumpRequest:connect(function()
        if InfiniteJumpEnabled then
            game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
        end
    end)
end)

--UNIVERSAL--
local Tab = Window:NewTab("Universal")
local Section = Tab:NewSection("Cmd-X Admin")
Section:NewButton("Cmd-X Admin", "Mostly Detectable", function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/CMD-X/CMD-X/master/Source'))()
end)
local Section = Tab:NewSection("Infinite Yield")
Section:NewButton("Infinite Yield", "Mostly Undetected", function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
end)
local Section = Tab:NewSection("Dark Dex/Dex")
Section:NewButton("Dark Dex/Dex", "Shows you game files, undetected", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/SpaceSpiffer/Scripts/main/Script5", true))()
end)
local Section = Tab:NewSection("Remote Spy/Simple Spy")
Section:NewButton("Remote Spy/Simple Spy", "Shows you remote events, undetected", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/luckywastakenwow/roblox-jp-script/main/rspy", true))()
end)

--DISCORD--
local Tab = Window:NewTab("Discord")
local Section = Tab:NewSection("Discord")
Section:NewButton("Copy Link", "Discord Link", function()
    print("Copied To Clipboard!")
    setclipboard("https://discord.gg/vracC6CYQp")
    toclipboard("https://discord.gg/vracC6CYQp")
end)

--CREDITS--
local Tab = Window:NewTab("Credits")
local Section = Tab:NewSection("Credits")
Section:NewButton('Made By Kaj#8453 and luckii#9523', "Credits", function()
    print("Clicked")
end)

--SETTINGS--
local Tab = Window:NewTab("Settings")
local Section = Tab:NewSection("Keybinds")
Section:NewKeybind("GUI Keybind Toggle", ":O", Enum.KeyCode.RightControl, function()
    Library:ToggleUI()
end)
