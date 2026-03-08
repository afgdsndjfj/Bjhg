-- lagger gui

print("hehe")

local Players = game:GetService("Players")

local player = Players.LocalPlayer

local playerGui = player:WaitForChild("PlayerGui")

local ScreenGui = Instance.new("ScreenGui")

ScreenGui.Name = "AstroHubGui"

ScreenGui.Parent = playerGui

ScreenGui.ResetOnSpawn = false

local Frame = Instance.new("Frame")

Frame.Size = UDim2.new(1, 0, 1, 0)

Frame.BackgroundTransparency = 1

Frame.Parent = ScreenGui

local TextLabel = Instance.new("TextLabel")

TextLabel.Parent = Frame

TextLabel.AnchorPoint = Vector2.new(0.5, 0.5)

TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)

TextLabel.BackgroundTransparency = 1

TextLabel.BorderSizePixel = 0

TextLabel.Position = UDim2.new(0.5, 0, 0.5, 0)

TextLabel.Size = UDim2.new(0, 408, 0, 152)

TextLabel.Font = Enum.Font.FredokaOne

TextLabel.Text = "AstroHub Lagger discord.gg/6szsrJh2Tb"

TextLabel.TextColor3 = Color3.fromRGB(98, 17, 148)

TextLabel.TextScaled = true

TextLabel.TextWrapped = true

spawn(function()

    function anticrashSkid(player)

        function anticrashChar(char)

            local hum = char:WaitForChild("Humanoid", 5)

            local anim = hum:WaitForChild("Animator", 5)

            anim.AnimationPlayed:Connect(function(track)

                track:AdjustSpeed(-math.huge)

                track:Stop()

            end)

            for _, v in anim:GetPlayingAnimationTracks() do

                v:AdjustSpeed(-math.huge)

                v:Stop()

            end

        end

        player.CharacterAdded:Connect(anticrashChar)

        if player.Character then

            anticrashChar(player.Character)

        end

    end

    local plrs = game:GetService("Players")

    for i, v in plrs:GetPlayers() do

        if v ~= plrs.LocalPlayer then

            anticrashSkid(v)

        end

    end

    plrs.PlayerAdded:Connect(anticrashSkid)

end)

spawn(function()

    while task.wait() do

        for i = 1, 5 do

            local anim = Instance.new("Animation")

            anim.AnimationId = `http{game:GetService("HttpService"):GenerateGUID()}=113437017590496`

            

            pcall(function()

                local track = game:GetService("Players").LocalPlayer.Character.Humanoid.Animator:LoadAnimation(anim)

                track:Play(9e9, 9e9, 9e9)

                game:GetService("RunService").PreRender:Wait()

                track:AdjustSpeed(-math.huge)

            end)

        end

    end

end)
