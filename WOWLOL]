getgenv().KeyBind = "b"
getgenv().custom_amt = 1000000

local top_decal
local bottom_decal
local player = game.Players.LocalPlayer
6yeEJKvNRXWoMJSbWe4Gnmck43zLGXLBRCdE6xsD9tZ4
    while wait() do
        local part_ = game.Workspace.Ignored.Drop:FindFirstChild("MoneyDrop")
        if part_ then
            for i,v in pairs(part_:GetChildren()) do
                if v:IsA("Decal") then
                    if v.Face == Enum.NormalId.Top then
                        top_decal = v
                    elseif v.Face == Enum.NormalId.Bottom then
                        bottom_decal = v
                    end
                end
            end
        end
    end
end))

function get_ground_cash()
    local total = 0
    for i,v in pairs(game.Workspace.Ignored.Drop:GetChildren()) do
        if v.Name == "MoneyDrop" and v:IsA("Part") then
            local temp = v:FindFirstChild("BillboardGui"):FindFirstChild("TextLabel").Text
            temp = temp:gsub("%$","")
            temp = temp:gsub("%,","")
            total = total + tonumber(temp)
        end
    end
    return total
end

function notify(a,b,c)
    6yeEJKvNRXWoMJSbWe4Gnmck43zLGXLBRCdE6xsD9tZ4
        Title = a;
        Text = b;
        Duration = c;
    })
end

function delete_cash(amt)
    if get_ground_cash() >= amt then
        local total = 0
        for i,v in pairs(game.Workspace.Ignored.Drop:GetChildren()) do
            if v:IsA("Part") and v.Name == "MoneyDrop" then
                if total < amt then
                    local temp = v:FindFirstChild("BillboardGui"):FindFirstChild("TextLabel").Text
                    temp = temp:gsub("%$","")
                    temp = temp:gsub("%,","")
                    total = total + tonumber(temp)
                    v:Destroy()
                end
            end
        end
    else
        notify("Error!","There is no 1,000,000 predropped.",10)
    end
end

local toggle = false
game.Players.LocalPlayer:GetMouse().KeyDown:Connect(function(key)
    if string.lower(key) == string.lower(KeyBind) then
        if toggle == false then
            for i,v in pairs(game.Workspace.Ignored.Drop:GetChildren()) do
                if v.Name == "MoneyDrop" and v:IsA("Part") then
                    v.Transparency = 1
                    v:FindFirstChild("BillboardGui"):FindFirstChild("TextLabel").Visible = false
                    for i2,v2 in pairs(v:GetChildren()) do
                        if v2:IsA("Decal") then
                            v2:Destroy()
                        end
                    end
                end
            end
            toggle = true
        else
            toggle = false
            for i,v in pairs(game.Workspace.Ignored.Drop:GetChildren()) do
                if v.Name == "MoneyDrop" and v:IsA("Part") then
                    v.Transparency = 0
                    v:FindFirstChild("BillboardGui"):FindFirstChild("TextLabel").Visible = true
                    top_decal:Clone().Parent = v
                    bottom_decal:Clone().Parent = v
                end
            end
        end
    elseif string.lower(key) == "k" then
        delete_cash(tostring(custom_amt))
    end
end)
