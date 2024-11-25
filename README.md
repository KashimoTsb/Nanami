-- Function to handle animation detection and replacement
local function handleAnimationDetection(animIdsToStop, replacementAnimId, animSpeed)
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoid = character:WaitForChild("Humanoid")

    local function onAnimPlayed(animationTrack)
        local animId = tonumber(string.match(animationTrack.Animation.AnimationId, "%d+"))
        
        for _, stopId in ipairs(animIdsToStop) do
            if animId == stopId then
                animationTrack:Stop()
                local replacementAnimation = Instance.new("Animation")
                replacementAnimation.AnimationId = "rbxassetid://" .. replacementAnimId
                local replacementTrack = humanoid:LoadAnimation(replacementAnimation)
                replacementTrack:Play()
                replacementTrack:AdjustSpeed(animSpeed) -- Adjust the speed of the replacement animation
                break
            end
        end
    end
    
    humanoid.AnimationPlayed:Connect(onAnimPlayed)
end

-- First set of animations
local firstAnimIdsToStop = {15290930205}
local firstReplacementAnimId = 14809836765
local firstAnimspeed = 2
handleAnimationDetection(firstAnimIdsToStop, firstReplacementAnimId, firstAnimspeed)

-- Second set of animations
local secondAnimIdsToStop = {15145462680}
local secondReplacementAnimId = 13633468484
local secondAnimspeed = 2
handleAnimationDetection(secondAnimIdsToStop, secondReplacementAnimId, secondAnimspeed)

-- Third set of animations
local thirdAnimIdsToStop = {15295895753}
local thirdReplacementAnimId = 13560306510
local thirdAnimspeed = 1.2
handleAnimationDetection(thirdAnimIdsToStop, thirdReplacementAnimId, thirdAnimspeed)

-- Fourth set of animations
local fourthAnimIdsToStop = {15311685628}
local fourthReplacementAnimId = 18440406788
local fourthAnimspeed = 1
handleAnimationDetection(fourthAnimIdsToStop, fourthReplacementAnimId, fourthAnimspeed)

local player = game.Players.LocalPlayer

local playerGui = player.PlayerGui

local hotbar = playerGui:FindFirstChild("Hotbar")

local backpack = hotbar:FindFirstChild("Backpack")

local hotbarFrame = backpack:FindFirstChild("Hotbar")

local baseButton = hotbarFrame:FindFirstChild("1").Base

local ToolName = baseButton.ToolName


ToolName.Text = "BlackFlash Lotus || ブラックフラッシュ・ロータス"

local player = game.Players.LocalPlayer

local playerGui = player.PlayerGui

local hotbar = playerGui:FindFirstChild("Hotbar")

local backpack = hotbar:FindFirstChild("Backpack")

local hotbarFrame = backpack:FindFirstChild("Hotbar")

local baseButton = hotbarFrame:FindFirstChild("2").Base

local ToolName = baseButton.ToolName


ToolName.Text = "Deadly Grip || デッドリーグリップ"

local player = game.Players.LocalPlayer

local playerGui = player.PlayerGui

local hotbar = playerGui:FindFirstChild("Hotbar")

local backpack = hotbar:FindFirstChild("Backpack")

local hotbarFrame = backpack:FindFirstChild("Hotbar")

local baseButton = hotbarFrame:FindFirstChild("3").Base

local ToolName = baseButton.ToolName


ToolName.Text = "Seven Sea Clash || セブンシークラッシュ"

local player = game.Players.LocalPlayer

local playerGui = player.PlayerGui

local hotbar = playerGui:FindFirstChild("Hotbar")

local backpack = hotbar:FindFirstChild("Backpack")

local hotbarFrame = backpack:FindFirstChild("Hotbar")

local baseButton = hotbarFrame:FindFirstChild("4").Base

local ToolName = baseButton.ToolName


ToolName.Text = "Cursed Ratio || 呪われた比率"
