if _G.Kaitun_VIP then
    

    Superhuman_A = _G.Melee.Superhuman
    Death_Step_A = _G.Melee.Death_Step
    Sharkman_Karate_A = _G.Melee.Sharkman_Karate
    Electric_Claw_A = _G.Melee.Electric_Claw
    Dragon_Talon_A = _G.Melee.Dragon_Talon
    
    Yama_A = _G.Sword.Yama
    DarkDagger_A = _G.Sword.DarkDagger
    Spikey_Trident_A = _G.Spikey_Trident
    BuddySword_A = _G.Sword.BuddySword
    Hallow_Scryte_A = _G.Sword.Hallow_Scryte
    Canvander_A = _G.Sword.Canvander
    
    _G.Setting_table = {
        Auto_Farm = false
    }
    Name_Me = game.Players.LocalPlayer
    local filename = tostring(Name_Me)..".txt"
    
    function savesetting()
        local json
        local HttpService = game:GetService("HttpService")
        if (writefile) then
            json = HttpService:JSONEncode(_G.Setting_table)
            writefile(filename, json)
        else
            print("-- Sorry You Noob --")
        end
    end
    
    function loadsetting()
        local HttpService = game:GetService("HttpService")
        if (readfile and isfile and isfile(filename)) then
            _G.Setting_table = HttpService:JSONDecode(readfile(filename))
            -- print("-- New Value --")
            for i,v in pairs(_G.Setting_table) do
                -- print(i,v)
            end
        end
    end
    loadsetting()
    
    if not game:IsLoaded() then 
        repeat game.Loaded:Wait() 
        until game:IsLoaded() end
        wait(math.random(1,5))
        Old_World = false
        New_World = false
        Three_World = false
        local placeId = game.PlaceId
        if placeId == 2753915549 then
            Old_World = true
        elseif placeId == 4442272183 then
            New_World = true
        elseif placeId == 7449423635 then
            Three_World = true
        end
        repeat wait(1)
    
        until game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Visible == true
        wait(1)
        if game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Visible == true then
            if _G.Teams == "Pirates" then
                for i,v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.MouseButton1Click)) do
                    v.Function()
                end
            elseif _G.Teams == "Marines" then
                for i,v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.MouseButton1Click)) do
                    v.Function()
                end
            else
                for i,v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.MouseButton1Click)) do
                    v.Function()
                end
            end
        end
    
        game.CoreGui.RobloxPromptGui.promptOverlay.DescendantAdded:Connect(function()
            local GUI = game.CoreGui.RobloxPromptGui.promptOverlay:FindFirstChild("ErrorPrompt")
            if GUI and TP_Ser == nil then
                if GUI.TitleFrame.ErrorTitle.Text == "Disconnected" then
                    if #game.Players:GetPlayers() <= 1 then
                        game.Players.LocalPlayer:Kick("\nRejoining...")
                        wait()
                        game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
                    else
                        game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, game.JobId, game.Players.LocalPlayer)
                    end
                end
            end
        end)
    
    local library = loadstring(game:HttpGet('https://raw.githubusercontent.com/x7Swiftz/Ui-Switch-HUb/main/README.md'))()
    local HoverPage = library:CreateWindow("Switch Hub ･ Premium™ Max™ Ultimate™ ",Enum.KeyCode.RightControl)
    
    local Status_P = HoverPage:CreateTab("Status")
    local Misc_P = HoverPage:CreateTab("Misc")
    
    local Status_M = Status_P:CreateSector("Main","Left")
    local MP_M = Status_P:CreateSector("Misc","Right")
    local Quest_M = Status_P:CreateSector("Quest","Left")
    local Melee_M = Status_P:CreateSector("Melee","Left")
    local Sword_M = Status_P:CreateSector("Sword","Left")
    local Open_M = Status_P:CreateSector("Open","Right")
    local Misc_M = Status_P:CreateSector("Gun","Right")
    local LE_M = Status_P:CreateSector("Legendary Sword","Right")
    
    function FPSBooster()
        local decalsyeeted = true -- Leaving this on makes games look shitty but the fps goes up by at least 20.
        local g = game
        local w = g.Workspace
        local l = g.Lighting
        local t = w.Terrain
        sethiddenproperty(l,"Technology",2)
        sethiddenproperty(t,"Decoration",false)
        t.WaterWaveSize = 0
        t.WaterWaveSpeed = 0
        t.WaterReflectance = 0
        t.WaterTransparency = 0
        l.GlobalShadows = false
        l.FogEnd = 9e9
        l.Brightness = 0
        settings().Rendering.QualityLevel = "Level01"
        for i, v in pairs(g:GetDescendants()) do
            if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then
                v.Material = "Plastic"
                v.Reflectance = 0
            elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
                v.Transparency = 1
            elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
                v.Lifetime = NumberRange.new(0)
            elseif v:IsA("Explosion") then
                v.BlastPressure = 1
                v.BlastRadius = 1
            elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
                v.Enabled = false
            elseif v:IsA("MeshPart") then
                v.Material = "Plastic"
                v.Reflectance = 0
                v.TextureID = 10385902758728957
            end
        end
        for i, e in pairs(l:GetChildren()) do
            if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
                e.Enabled = false
            end
        end
    end
    MP_M:AddToggle("FPS Booster",_G.FPS_Booster,function(vu)
        FastAttack = vu
        if FastAttack == true then
            FPSBooster()
        end
    end)
    local White = MP_M:AddToggle("White Screen", _G.White_Screen, function(vu)
        White_Screen = vu
        if White_Screen then
            game:GetService("RunService"):Set3dRenderingEnabled(false)
        else
            game:GetService("RunService"):Set3dRenderingEnabled(true)
        end
    end)
    White:AddKeybind(Enum.KeyCode.Y, flag)
    
    if Old_World then
        WOP = 1
    elseif New_World then
        WOP = 2
    elseif Three_World then
        WOP = 3
    end
    Status_M:AddLabel("Name : "..tostring(game.Players.LocalPlayer))
    Status_M:AddLabel("World : "..tostring(WOP))
    
    Open_M:AddButton("Open Fruit Inventory",function()
    
    end)
    Open_M:AddButton("Open Fruit Awake",function()
    
    end)
    Open_M:AddButton("Open Fruit Shop",function()
    
    end)
    Open_M:AddButton("Open Item Inventory",function()
    
    end)
    
    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
        Quest_M:AddLabel("✅ : Open Don Swan Quest")
    else
        Quest_M:AddLabel("❌ : Open Don Swan Quest")
    end
    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
        Quest_M:AddLabel("✅ : Bartilo Quest")
    else
        Quest_M:AddLabel("❌ : Bartilo Quest")
    end
    
    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman") == 2 then
        Melee_M:AddLabel("✅ : Superhuman")
    else
        Melee_M:AddLabel("❌ : Superhuman")
    end
    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 2 then
        Melee_M:AddLabel("✅ : Death Step")
    else
        Melee_M:AddLabel("❌ : Death Step")
    end
    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate") == 2 then
        Melee_M:AddLabel("✅ : Sharkman Karate")
    else
        Melee_M:AddLabel("❌ : Sharkman Karate")
    end
    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw") == 2 then
        Melee_M:AddLabel("✅ : Electric Claw")
    else
        Melee_M:AddLabel("❌ : Electric Claw")
    end
    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon") == 1 or game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon") == 2 then
        Melee_M:AddLabel("✅ : Dragon Talon")
    else
        Melee_M:AddLabel("❌ : Dragon Talon")
    end
    local YM = Sword_M:AddLabel("❌ : Yama")
    local CVD = Sword_M:AddLabel("❌ : Cavander")
    local DDG = Sword_M:AddLabel("❌ : Dark Dagger")
    local BDS = Sword_M:AddLabel("❌ : Buddy Sword")
    local HLS = Sword_M:AddLabel("❌ : Hallow Scryte")
    local SPK = Sword_M:AddLabel("❌ : Spikey Trident")
    
    local KBC = Misc_M:AddLabel("❌ : Kabucha")
    local ACD = Misc_M:AddLabel("❌ : Acidum Rifle")
    local SPKB = Misc_M:AddLabel("❌ : Serpent Bow")
    
    local SHI = LE_M:AddLabel("❌ : Shisui")
    local SDI = LE_M:AddLabel("❌ : Saddi")
    local WND = LE_M:AddLabel("❌ : Wando")
    
    game:GetService("Players").LocalPlayer.PlayerGui.Main.Inventory.Visible = true
    wait(1)
    for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main.Inventory.Container.Current.ScrollingFrame.Frame:GetChildren()) do
        for i2,v2 in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main.Inventory.Container.Stored.ScrollingFrame.Frame:GetChildren()) do
            if v.Name == "Dark Dagger" or v2.Name == "Dark Dagger" then
                DDG:Set("✅ : Dark Dagger")
            end
            if v.Name == "Buddy Sword" or v2.Name == "Buddy Sword" then
                BDS:Set("✅ : Buddy Sword")
            end
            if v.Name == "Hallow Scryte" or v2.Name == "Hallow Scryte" then
                HLS:Set("✅ : Hallow Scryte")
            end
            if v.Name == "Spikey Trident" or v2.Name == "Spikey Trident" then
                SPK:Set("✅ : Spikey Trident")
            end
            if v.Name == "Yama" or v2.Name == "Yama" then
                YM:Set("✅ : Yama")
            end
            if v.Name == "Canvander" or v2.Name == "Canvander" then
                CVD:Set("✅ : Canvander")
            end
            if v.Name == "Kabucha" or v2.Name == "Kabucha" then
                KBC:Set("✅ : Kabucha")
            end
            if v.Name == "Acidum Rifle" or v2.Name == "Acidum Rifle" then
                ACD:Set("✅ : Acidum Rifle")
            end
            if v.Name == "Serpent Bow" or v2.Name == "Serpent Bow" then
                SPKB:Set("✅ : Serpent Bow")
            end
            if v.Name == "Shisui" or v2.Name == "Shisui" then
                SHI:Set("✅ : Shisui")
            end
            if v.Name == "Saddi" or v2.Name == "Saddi" then
                SDI:Set("✅ : Saddi")
            end
            if v.Name == "Wando" or v2.Name == "Wando" then
                WND:Set("✅ : Wando")
            end
        end
    end
    game:GetService("Players").LocalPlayer.PlayerGui.Main.Inventory.Visible = false
    
    if _G.Number == nil then
    
    else
        setfpscap(_G.Number)
    end
    
    spawn(function()
        while wait() do
            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                if tostring(v2.ToolTip) == "Melee" then
                    Melee_E = v2.Name
                    wait(5)
                end
            end
        end
    end)
    
    _G.Kaitun_VIP = true
    if _G.Kaitun_VIP then
        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
        FastAttack = true
        Redeem = true
        BringFruit = true
        Auto_Buy_Random_Fruit = true
        Sniper_Fruit = true
        Inventory_Fruit = true
        if Lv < 2300 then
            Auto_Farm = true
            if Old_World then
                Saber_Farm = true
                Buy_All = true
                Auto_New_World = true
            elseif New_World then
                Open_Don_Swan = true
                Bartlio_Farm = true
            end
        elseif Lv >= 2300 then
            _G.Hop = true
            if Superhuman_A then
                _G.Hop_Superhuman = true
            end
            if Sharkman_Karate_A then
                _G.Hop_Sharkman_Karate = true
            end
            if Death_Step_A then
                _G.Hop_Death_Step = true
            end
            if Dragon_Talon_A then
                _G.Hop_Dragon_Talon = true
            end
            if Electric_Claw_A then
                _G.Hop_Electric_Claw = true
            end
    
            if BuddySword_A then
                _G.Hop_BuddySword = true
            end
            if Spikey_Trident_A then
                _G.Hop_SpikeyTrident = true
            end
            if Hallow_Scryte_A then
                _G.Hop_HallowScryte = true
            end
            if Yama_A then
                _G.Hop_Yama = true
            end
            if Canvander_A then
                _G.Hop_Canvander = true
            end
            if DarkDagger_A then
                _G.Hop_DarkDagger = true
            end
        end
    end
    
    spawn(function()
        while wait(2) do
            if _G.Hop then
                if _G.Hop_Saber and _G.Hop_Saber_Ex == nil then
                    Saber_Farm = true
                elseif _G.Hop_PoleV1 and _G.Hop_PoleV1_Ex == nil then
                    Pole_V1_Hop = true
                elseif _G.Hop_Superhuman and _G.Hop_Superhuman_Ex == nil then
                    Superhuman_A = true
                elseif _G.Hop_Sharkman_Karate and _G.Hop_Sharkman_Karate_Ex == nil then
                    Sharkman_Karate_A = true
                elseif _G.Hop_Death_Step and _G.Hop_Death_Step_Ex == nil then
                    Death_Step_A = true
                elseif _G.Hop_Electric_Claw and _G.Hop_Electric_Claw_Ex == nil then
                    Electric_Claw_A = true
                elseif _G.Hop_Dragon_Talon and _G.Hop_Dragon_Talon_Ex == nil then
                    Dragon_Talon_A = true
                elseif _G.Hop_BuddySword and _G.Hop_BuddySword_Ex == nil then
                    BuddySword_A = true
                elseif _G.Hop_DarkDagger and _G.Hop_DarkDagger_Ex == nil then
                    DarkDagger_A = true
                elseif _G.Hop_HallowScryte and _G.Hop_HallowScryte_Ex == nil then
                    Hallow_Scryte_A = true
                elseif _G.Hop_SpikeyTrident and _G.Hop_SpikeyTrident_Ex == nil then
                    Spikey_Trident_A = true
                elseif _G.Hop_Yama and _G.Hop_Yama_Ex == nil then
                    Yama_A = true
                elseif _G.Hop_DarkDagger and _G.Hop_DarkDagger_Ex == nil then
                    Canvander_A = true
                elseif _G.Hop_Raid and _G.Hop_Raid_Ex == nil then
                    AutoRaid = true
                elseif _G.Hop_Farm_Boss and _G.Hop_Farm_Boss_Ex == nil then
                    Auto_Farm_Boss = true
                elseif _G.Hop_Farm_All_Boss and _G.Hop_Farm_All_Boss_Ex == nil then
                    Auto_Farm_Boss_All = true
                elseif _G.Hop_Elite_Hunter and _G.Hop_Elite_Hunter_Ex == nil then
                    EliteHunter = true
                elseif _G.Hop_Buy_Legendary_Sword and _G.Hop_Buy_Legendary_Sword_Ex == nil then
                    Auto_Buy_Legendary_Sword = true
                elseif _G.Hop_Bring_Fruit and _G.Hop_Bring_Fruit_Ex == nil then
                    BringFruit = true
                else
                    HopServer()
                    wait(25)
                end
            end
        end
    end)
    
    
    function HopServer()
        game.StarterGui:SetCore("SendNotification", {
            Title = "HopServer", 
            Text = "กำลังหาเซิฟ",
            Icon = "http://www.roblox.com/asset/?id=9370135749",
            Duration = 15
        })
        local PlaceID = game.PlaceId
        local AllIDs = {}
        local foundAnything = ""
        local actualHour = os.date("!*t").hour
        local Deleted = false
        function TPReturner()
            local Site;
            if foundAnything == "" then
                Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
            else
                Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
            end
            local ID = ""
            if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
                foundAnything = Site.nextPageCursor
            end
            local num = 0;
            for i,v in pairs(Site.data) do
                local Possible = true
                ID = tostring(v.id)
                game.StarterGui:SetCore("SendNotification", {
                    Title = "HopServer", 
                    Text = "Players : " ..tonumber(v.playing),
                    Icon = "http://www.roblox.com/asset/?id=9370135749",
                    Duration = 1.5
                })
                if tonumber(v.maxPlayers) > tonumber(v.playing) then
                    for _,Existing in pairs(AllIDs) do
                        if num ~= 0 then
                            if ID == tostring(Existing) then
                                Possible = false
                            end
                        else
                            if tonumber(actualHour) ~= tonumber(Existing) then
                                local delFile = pcall(function()
                                    -- delfile("NotSameServers.json")
                                    AllIDs = {}
                                    table.insert(AllIDs, actualHour)
                                end)
                            end
                        end
                        num = num + 1
                    end
                    if Possible == true then
                        table.insert(AllIDs, ID)
                        wait()
                        pcall(function()
                            TP_Ser = true
                            -- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
                            wait()
                            game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
                        end)
                        wait(.1)
                    end
                end
            end
        end
        function Bring()
            while wait(.2) do
                pcall(function()
                    TPReturner()
                    if foundAnything ~= "" then
                        TPReturner()
                    end
                end)
            end
        end
        Bring()
    end
    
    local PlaceID = game.PlaceId
        local AllIDs = {}
        local foundAnything = ""
        local actualHour = os.date("!*t").hour
        local Deleted = false
        local File = pcall(function()
            AllIDs = game:GetService('HttpService'):JSONDecode(readfile("NotSameServers.json"))
        end)
        if not File then
            table.insert(AllIDs, actualHour)
            writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
        end
        
        function HopLowerServer()
            game.StarterGui:SetCore("SendNotification", {
                Title = "Hop LowServer", 
                Text = "กำลังหาเซิฟ",
                Icon = "http://www.roblox.com/asset/?id=9370135749",
                Duration = 10
            })
            TP_Ser = true
            local maxplayers, gamelink, goodserver, data_table = math.huge, "https://games.roblox.com/v1/games/" .. game.PlaceId .. "/servers/Public?sortOrder=Asc&limit=100"
            if not _G.FailedServerID then _G.FailedServerID = {} end
            local function serversearch()
                data_table = game:GetService"HttpService":JSONDecode(game:HttpGetAsync(gamelink))
                for _, v in pairs(data_table.data) do
                    pcall(function()
                        if type(v) == "table" and v.id and v.playing and tonumber(maxplayers) > tonumber(v.playing) and not table.find(_G.FailedServerID, v.id) then
                            game.StarterGui:SetCore("SendNotification", {
                                Title = "Hop LowServer", 
                                Text = "Players : "..tostring(v.playing),
                                Icon = "http://www.roblox.com/asset/?id=9370135749",
                                Duration = 2.5
                            })
                           _G.Teleport = true
                            maxplayers = v.playing
                            goodserver = v.id
                        end
                    end)
                end
            end
            function getservers()
                pcall(serversearch)
                for i, v in pairs(data_table) do
                    if i == "nextPageCursor" then
                        if gamelink:find"&cursor=" then
                            local a = gamelink:find"&cursor="
                            local b = gamelink:sub(a)
                            gamelink = gamelink:gsub(b, "")
                        end
                        gamelink = gamelink .. "&cursor=" .. v
                        pcall(getservers)
                    end
                end
            end
            pcall(getservers)
            if goodserver == game.JobId or maxplayers == #game:GetService"Players":GetChildren() - 1 then
            end
            table.insert(_G.FailedServerID, goodserver)
            TP_Ser = true
            game:GetService"TeleportService":TeleportToPlaceInstance(game.PlaceId, goodserver)
        end
    
    spawn(function()
        while wait(5) do
            if Buy_All and Have_I == nil then
                local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                if Lv >= 600 and Have_I == nil then
                    local args = {
                        [1] = "BuyHaki",
                        [2] = "Geppo"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    local args = {
                        [1] = "BuyHaki",
                        [2] = "Soru"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    local args = {
                        [1] = "BuyHaki",
                        [2] = "Buso"
                    }
                
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))   
                    local args = {
                        [1] = "KenTalk",
                        [2] = "Buy"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Bisento")
                
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual-Headed Blade")
                    
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Soul Cane")
                
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Triple Katana")
                
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Pipe")
                
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual Katana")
                
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Iron Mace")
                    Have_I = true
                end
            end
        end
    end)
    
    spawn(function()
        while wait(.2) do
            if Auto_Buy_Random_Fruit then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
                wait(20)
            end
        end
    end)
    
    spawn(function()
        while wait(30) do
            if Sniper_Fruit then
                for s,f in pairs(_G.Select_Fruit) do
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PurchaseRawFruit",f)
                end
            end
        end
    end)
    
    spawn(function()
        while wait(.2) do
            if BringFruit then
                for i,v6 in pairs(game:GetService("Workspace"):GetChildren()) do
                    if v6:IsA ("Tool") and (v6.Handle.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 20000 then
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v6.Handle.CFrame
                        v6.Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                    end
                end
            end
        end
    end)
    if _G.Select_Fruit == nil then
        _G.Select_Fruit = {
            "777","888","999"
        }
    end
    _G.Fruit_Name = {}
    for i,v in pairs(_G.Select_Fruit) do
        if v == "Dark-Dark" then
            table.insert(_G.Fruit_Name,"Dark Fruit")
        end
        if v == "Sand-Sand" then
            table.insert(_G.Fruit_Name,"Sand Fruit")
        end
        if v == "Magma-Magma" then
            table.insert(_G.Fruit_Name,"Magma Fruit")
        end
        if v == "Door-Door" then
            table.insert(_G.Fruit_Name,"Door Fruit")
        end
        if v == "Shadow-Shadow" then
            table.insert(_G.Fruit_Name,"Shadow Fruit")
        end
        if v == "Venom-Venom" then
            table.insert(_G.Fruit_Name,"Venom Fruit")
        end
        if v == "Rumble-Rumble" then
            table.insert(_G.Fruit_Name,"Rumble Fruit")
        end
        if v == "Bird-Bird: Phoenix" then
            table.insert(_G.Fruit_Name,"Bird: Phoenix Fruit")
        end
        if v == "String-String" then
            table.insert(_G.Fruit_Name,"String Fruit")
        end
        if v == "Human-Human: Buddha" then
            table.insert(_G.Fruit_Name,"Human-Human: Buddha Fruit")
        end
        if v == "Dragon-Dragon" then
            table.insert(_G.Fruit_Name,"Dragon Fruit")
        end
        if v == "Light-Light" then
            table.insert(_G.Fruit_Name,"Light Fruit")
        end
        if v == "Quake-Quake" then
            table.insert(_G.Fruit_Name,"Quake Fruit")
        end
        if v == "Soul-Soul" then
            table.insert(_G.Fruit_Name,"Soul Fruit")
        end
        if v == "Ice-Ice" then
            table.insert(_G.Fruit_Name,"Ice Fruit")
        end
    end
    
    spawn(function()
        while wait(1) do
            if Open_Don_Swan then
                local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                if Lv >= 1100 then
                    pcall(function()
                        local Fruit_List = {
                            "Quake-Quake",
                            "Quake Fruit",
                            "Human-Human: Buddha",
                            "Human-Human: Buddha Fruit",
                            "String-String",
                            "String Fruit",
                            "Rumble-Rumble",
                            "Rumble Fruit",
                            "Paw Fruit",
                            "Paw-Paw",
                            "Gravity Fruit",
                            "Gravity-Gravity",
                            "Dough Fruit",
                            "Dough-Dough",
                            "Shadow Fruit",
                            "Shadow-Shadow",
                            "Shadow Fruit",
                            "Venom-Venom",
                            "Venom Fruit",
                            "Control Fruit",
                            "Control-Control",
                            "Dragon Fruit",
                            "Dragon-Dragon"
                        }
                        game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Visible = true
                        local Value_Fruit = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                        if Value_Fruit == _G.Select_Fruit[1] or Value_Fruit == _G.Select_Fruit[2] or Value_Fruit == _G.Select_Fruit[3] or Value_Fruit == _G.Select_Fruit[4] or Value_Fruit == _G.Select_Fruit[5] or not CH:FindFirstChild(_G.Fruit_Name[1]) and not CH:FindFirstChild(_G.Fruit_Name[2]) and not CH:FindFirstChild(_G.Fruit_Name[3]) and not CH:FindFirstChild(_G.Fruit_Name[4]) and not CH:FindFirstChild(_G.Fruit_Name[5]) and not BP:FindFirstChild(_G.Fruit_Name[1]) and not BP:FindFirstChild(_G.Fruit_Name[2]) and not BP:FindFirstChild(_G.Fruit_Name[3]) and not BP:FindFirstChild(_G.Fruit_Name[4]) and not BP:FindFirstChild(_G.Fruit_Name[5]) then
                            for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Container.Stored.ScrollingFrame.Frame:GetChildren()) do
                                if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
                                    if string.find(v.Name,"-") then
                                        Inventory_Fruit = false
                                        Auto_Farm = false
                                        wait(1)
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v.Name)
                                        POP = true
                                        AutoRaid = true
                                        wait(1)
                                        game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Visible = false
                                    end
                                else
                                    if v.Name == Fruit_List[1] or v.Name == Fruit_List[3] or v.Name == Fruit_List[5] or v.Name == Fruit_List[7] or v.Name == Fruit_List[10] or v.Name == Fruit_List[12] or v.Name == Fruit_List[14] or v.Name == Fruit_List[16] or v.Name == Fruit_List[18] or v.Name == Fruit_List[21] or v.Name == Fruit_List[23] then
                                        Inventory_Fruit = false
                                        wait(1)
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v.Name)
                                        for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                                            if v2:IsA("Tool") then
                                                if v2.Name == Fruit_List[2] or v2.Name == Fruit_List[4] or v2.Name == Fruit_List[6] or v2.Name == Fruit_List[8] or v2.Name == Fruit_List[9] or v2.Name == Fruit_List[11] or v2.Name == Fruit_List[13] or v2.Name == Fruit_List[15] or v2.Name == Fruit_List[19] or v2.Name == Fruit_List[20] or v2.Name == Fruit_List[22] then
                                                    Auto_Farm = false
                                                    EquipWeapon(v2.Name)
                                                    wait(1)
                                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
                                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
                                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
                                                    wait(2)
                                                    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
                                                        HopServer()
                                                        wait(25)
                                                    end
                                                end
                                            end
                                        end
                                    else
                                        if string.find(v.Name,"-") then
                                            Inventory_Fruit = false
                                            Auto_Farm = false
                                            wait(1)
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v.Name)
                                            POP = true
                                            AutoRaid = true
                                            wait(1)
                                            game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Visible = false
                                        end
                                    end
                                end
                            end
                        else
                            if Value_Fruit ~= _G.Select_Fruit[1] and Value_Fruit ~= _G.Select_Fruit[2] and Value_Fruit ~= _G.Select_Fruit[3] and Value_Fruit ~= _G.Select_Fruit[4] and Value_Fruit ~= _G.Select_Fruit[5] then
                                for i8,v8 in pairs(_G.Fruit_Name) do
                                    for i9,v9 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                                        if v9:IsA("Tool") then
                                            if string.find(v9.Name,"Fruit") then
                                                if v9.Name == v8 then
                                                    Clip = true
                                                    Auto_Farm = false
                                                    EquipWeapon(v9.Name)
                                                    wait(1)
                                                    game:GetService("Players").LocalPlayer.Character:FindFirstChild(v9.Name).EatRemote:InvokeServer()
                                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                                                    wait(2)
                                                    Clip = false
                                                    Auto_Farm = true
                                                end
                                            end
                                        end
                                    end
                                end
                            end
                            local Value_Fruit = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                            if Value_Fruit ~= _G.Select_Fruit[1] and Value_Fruit ~= _G.Select_Fruit[2] and Value_Fruit ~= _G.Select_Fruit[3] and Value_Fruit ~= _G.Select_Fruit[4] and Value_Fruit ~= _G.Select_Fruit[5] then
                                for i8,v8 in pairs(_G.Fruit_Name) do
                                    for i9,v9 in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
                                        if v9:IsA("Tool") then
                                            if string.find(v9.Name,"Fruit") then
                                                if v9.Name == v8 then
                                                    Clip = true
                                                    Auto_Farm = false
                                                    EquipWeapon(v9.Name)
                                                    wait(1)
                                                    game:GetService("Players").LocalPlayer.Character:FindFirstChild(v9.Name).EatRemote:InvokeServer()
                                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                                                    wait(2)
                                                    Clip = false
                                                    Auto_Farm = true
                                                end
                                            end
                                        end
                                    end
                                end
                            end
                        end
                    end)
                end
            end
        end
    end)
    
    spawn(function()
        while wait(1) do
            if Inventory_Fruit then
                local CH = game.Players.LocalPlayer.Character
                local BP = game.Players.LocalPlayer.Backpack
                local Value_Fruit = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                    if Value_Fruit == _G.Select_Fruit[1] or Value_Fruit == _G.Select_Fruit[2] or Value_Fruit == _G.Select_Fruit[3] or Value_Fruit == _G.Select_Fruit[4] or Value_Fruit == _G.Select_Fruit[5] or not CH:FindFirstChild(_G.Fruit_Name[1]) and not CH:FindFirstChild(_G.Fruit_Name[2]) and not CH:FindFirstChild(_G.Fruit_Name[3]) and not CH:FindFirstChild(_G.Fruit_Name[4]) and not CH:FindFirstChild(_G.Fruit_Name[5]) and not BP:FindFirstChild(_G.Fruit_Name[1]) and not BP:FindFirstChild(_G.Fruit_Name[2]) and not BP:FindFirstChild(_G.Fruit_Name[3]) and not BP:FindFirstChild(_G.Fruit_Name[4]) and not BP:FindFirstChild(_G.Fruit_Name[5]) then
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bomb Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bomb Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bomb-Bomb")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spike Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spike Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spike-Spike")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Chop Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Chop Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Chop-Chop")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spring Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spring Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spring-Spring")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Kilo Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Kilo Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Kilo-Kilo")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Smoke Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Smoke Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Smoke-Smoke")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spin Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spin Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spin-Spin")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Flame-Flame")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Falcon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Falcon Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Falcon")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Ice-Ice")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Sand-Sand")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dark-Dark")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Revive Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Revive Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Revive-Revive")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Diamond Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Diamond Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Diamond-Diamond")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Light-Light")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Love Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Love Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Love-Love")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rubber Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rubber Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rubber-Rubber")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Barrier Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Barrier Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Barrier-Barrier")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Magma-Magma")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Door Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Door Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Door-Door")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Quake-Quake")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Human-Human: Buddha")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("String Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","String-String")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Phoenix")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rumble-Rumble")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Paw Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Paw Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Paw-Paw")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Gravity Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Gravity Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Gravity-Gravity")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dough Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dough Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dough-Dough")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Shadow Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Shadow Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Shadow-Shadow")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Venom Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Venom-Venom")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Control Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Control Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Control-Control")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dragon-Dragon")
                            wait(1)
                        end
                        if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Soul Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Soul Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Soul-Soul")
                            wait(1)
                        end
                    else
                        local Value_Fruit = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                        if Value_Fruit ~= _G.Select_Fruit[1] and Value_Fruit ~= _G.Select_Fruit[2] and Value_Fruit ~= _G.Select_Fruit[3] and Value_Fruit ~= _G.Select_Fruit[4] and Value_Fruit ~= _G.Select_Fruit[5] then
                            for i8,v8 in pairs(_G.Fruit_Name) do
                                for i9,v9 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                                    if v9:IsA("Tool") then
                                        if string.find(v9.Name,"Fruit") then
                                            if v9.Name == v8 then
                                                Clip = true
                                                Auto_Farm = false
                                                EquipWeapon(v9.Name)
                                                wait(1)
                                                game:GetService("Players").LocalPlayer.Character:FindFirstChild(v9.Name).EatRemote:InvokeServer()
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                                                wait(2)
                                                Clip = false
                                                Auto_Farm = true
                                            end
                                        end
                                    end
                                end
                            end
                        end
                        local Value_Fruit = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                        if Value_Fruit ~= _G.Select_Fruit[1] and Value_Fruit ~= _G.Select_Fruit[2] and Value_Fruit ~= _G.Select_Fruit[3] and Value_Fruit ~= _G.Select_Fruit[4] and Value_Fruit ~= _G.Select_Fruit[5] then
                            for i8,v8 in pairs(_G.Fruit_Name) do
                                for i9,v9 in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
                                    if v9:IsA("Tool") then
                                        if string.find(v9.Name,"Fruit") then
                                            if v9.Name == v8 then
                                                Clip = true
                                                Auto_Farm = false
                                                EquipWeapon(v9.Name)
                                                wait(1)
                                                game:GetService("Players").LocalPlayer.Character:FindFirstChild(v9.Name).EatRemote:InvokeServer()
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                                                wait(2)
                                                Clip = false
                                                Auto_Farm = true
                                            end
                                        end
                                    end
                                end
                            end
                        end
                    end
            end
        end
    end)
    
    spawn(function()
        game:GetService("RunService").Heartbeat:Connect(function()
            pcall(function()
                local MyLevel = game.Players.LocalPlayer.Data.Level.Value
                if StatrMagnet then
                    for y,x in pairs(game.Workspace.Enemies:GetChildren()) do
                        if not string.find(x.Name,"Boss") and(x.HumanoidRootPart.Position-_G.PosMon.Position).Magnitude <= 300 then
                            if x.Humanoid:FindFirstChild("Animator") then
                                x.Humanoid.Animator:Destroy()
                            end
                            x.HumanoidRootPart.CanCollide = false
                            x.HumanoidRootPart.CFrame = _G.PosMon
                            x.HumanoidRootPart.Size = Vector3.new(5,5,5)
                            sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
                        end
                    end
                end
            end)
        end)
    end)
    
    spawn(function()
        while wait(3) do
            character = game.Players.LocalPlayer.Character 
            if Auto_Farm or Auto_Farm_Bone or  Ability_Human_V3 or Ability_Fish_V3 or Ability_Mink_V1  or Ability_Mink_V3 or Ability_Skypie_V3 or Saber_Farm or Pole_V1_Hop or Ability_Mink_V2 or Auto_Farm_Sword or Auto_Farm_Melee or Auto_Farm_Fruit or Clip or Mix_Farm or Bartlio_Farm or Saber_Farm or NextIsland or Auto_New_World or Auto_Three_World then
                pcall(function()
                    for _, v in pairs(character:GetChildren()) do
                        if v:IsA("BasePart") then
                            v.CanCollide = false
                        end
                    end
                end)
            end
        end
    end)
    
    spawn(function()
        while task.wait() do
            if Auto_Farm or Auto_Farm_Bone or  Ability_Human_V3 or Ability_Fish_V3 or Ability_Mink_V1  or Ability_Mink_V3 or Ability_Skypie_V3 or Saber_Farm or Pole_V1_Hop or Ability_Mink_V2 or Auto_Farm_Sword or Auto_Farm_Melee or Auto_Farm_Fruit or Clip or Mix_Farm or Bartlio_Farm or Saber_Farm or NextIsland or Auto_New_World or Auto_Three_World then
                if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyVelocity") then 
                    local L_1 = Instance.new("BodyVelocity") 
                    L_1.Name = "BodyGyrozz"
                    L_1.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart 
                    L_1.MaxForce=Vector3.new(100000,100000,100000)
                    L_1.Velocity=Vector3.new(0,0,0) 
                end
            else
                if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyGyrozz") then
                    game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyGyrozz"):Destroy()
                end
            end 
        end
    end)
    
    
    function TP(P1)
        local Speed = 10
        local Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
        if Distance < 150 then
            Speed = 2000
        elseif Distance < 300 then
            Speed = 1500
        elseif Distance < 350 then
            Speed = 1000
        elseif Distance < 1000 then
            Speed = 350
        elseif Distance >= 1000 then
            Speed = 300
        end
        game:GetService("TweenService"):Create(
            game.Players.LocalPlayer.Character.HumanoidRootPart,
            TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
            {CFrame = P1}
        ):Play()
    end
    
    function TP2(P1)
        local Speed = 10
        local Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
        if Distance < 150 then
            Speed = 200
        elseif Distance < 300 then
            Speed = 225
        elseif Distance < 500 then
            Speed = 200
        elseif Distance < 1000 then
            Speed = 170
        elseif Distance >= 1000 then
            Speed = 200
        end
        Clip = true
        game:GetService("TweenService"):Create(
            game.Players.LocalPlayer.Character.HumanoidRootPart,
            TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
            {CFrame = P1}
        ):Play()
        Clip = false
    end
    
    spawn(function()
        game:GetService("Players").LocalPlayer.Idled:connect(function()
            VirtualUser:CreateButton2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
            wait(1)
            VirtualUser:CreateButton2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
        end)
    end)
    
    function EquipWeapon(ToolSe)
        if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
            local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
            wait(.4)
            game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
        end
    end
    
    local Fast = getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))
    local Lop = Fast[2]
    local yedkuy112 = require(game.Players.LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
    
    spawn(function()
        game:GetService("RunService").Heartbeat:Connect(function()
            pcall(function()
                if FastAttack then
                    if Auto_Farm or Auto_Farm_Melee then
                        yedkuy112.CameraShakeInstance.CameraShakeState.Inactive = 0
                        Lop.activeController.blocking = false
                        Lop.activeController.timeToNextBlock = 0
                        Lop.activeController.attacking = false
                        Lop.activeController.increment = 3
                        Lop.activeController.hitboxMagnitude = 50
                        Lop.activeController.timeToNextAttack = -(math.huge*math.huge) -- math.huge^math.huge
                        Lop.activeController:attack()
                    else
                        yedkuy112.CameraShakeInstance.CameraShakeState.Inactive = 0
                        Lop.activeController.blocking = false
                        Lop.activeController.timeToNextBlock = 0
                        Lop.activeController.attacking = false
                        Lop.activeController.increment = 3
                        Lop.activeController.hitboxMagnitude = 50
                        Lop.activeController.timeToNextAttack = -(math.huge*math.huge) -- math.huge^math.huge
                    end
                end
            end)
        end)
    end)
    
        function CheckLevel()
            local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
            if Old_World then
                if Lv == 1 or Lv <= 9 or SelectMonster == "Bandit [Lv. 5]" then -- Bandit
                    Ms = "Bandit [Lv. 5]"
                    NameQuest = "BanditQuest1"
                    QuestLv = 1
                    NameMon = "Bandit"
                    CFrameQ = CFrame.new(1060.9383544922, 16.455066680908, 1547.7841796875)
                    CFrameMon = CFrame.new(1038.5533447266, 41.296249389648, 1576.5098876953)
                elseif Lv == 10 or Lv <= 14 or SelectMonster == "Monkey [Lv. 14]" then -- Monkey
                    Ms = "Monkey [Lv. 14]"
                    NameQuest = "JungleQuest"
                    QuestLv = 1
                    NameMon = "Monkey"
                    CFrameQ = CFrame.new(-1601.6553955078, 36.85213470459, 153.38809204102)
                    CFrameMon = CFrame.new(-1448.1446533203, 50.851993560791, 63.60718536377)
                elseif Lv == 15 or Lv <= 29 or SelectMonster == "Gorilla [Lv. 20]" then -- Gorilla
                    Ms = "Gorilla [Lv. 20]"
                    NameQuest = "JungleQuest"
                    QuestLv = 2
                    NameMon = "Gorilla"
                    CFrameQ = CFrame.new(-1601.6553955078, 36.85213470459, 153.38809204102)
                    CFrameMon = CFrame.new(-1142.6488037109, 40.462348937988, -515.39227294922)
                elseif Lv == 30 or Lv <= 39 or SelectMonster == "Pirate [Lv. 35]" then -- Pirate
                    Ms = "Pirate [Lv. 35]"
                    NameQuest = "BuggyQuest1"
                    QuestLv = 1
                    NameMon = "Pirate"
                    CFrameQ = CFrame.new(-1140.1761474609, 4.752049446106, 3827.4057617188)
                    CFrameMon = CFrame.new(-1201.0881347656, 40.628940582275, 3857.5966796875)
                elseif Lv == 40 or Lv <= 59 or SelectMonster == "Brute [Lv. 45]" then -- Brute
                    Ms = "Brute [Lv. 45]"
                    NameQuest = "BuggyQuest1"
                    QuestLv = 2
                    NameMon = "Brute"
                    CFrameQ = CFrame.new(-1140.1761474609, 4.752049446106, 3827.4057617188)
                    CFrameMon = CFrame.new(-1387.5324707031, 24.592035293579, 4100.9575195313)
                elseif Lv == 60 or Lv <= 74 or SelectMonster == "Desert Bandit [Lv. 60]" then -- Desert Bandit
                    Ms = "Desert Bandit [Lv. 60]"
                    NameQuest = "DesertQuest"
                    QuestLv = 1
                    NameMon = "Desert Bandit"
                    CFrameQ = CFrame.new(896.51721191406, 6.4384617805481, 4390.1494140625)
                    CFrameMon = CFrame.new(984.99896240234, 16.109552383423, 4417.91015625)
                elseif Lv == 75 or Lv <= 89 or SelectMonster == "Desert Officer [Lv. 70]" then -- Desert Officer
                    Ms = "Desert Officer [Lv. 70]"
                    NameQuest = "DesertQuest"
                    QuestLv = 2
                    NameMon = "Desert Officer"
                    CFrameQ = CFrame.new(896.51721191406, 6.4384617805481, 4390.1494140625)
                    CFrameMon = CFrame.new(1547.1510009766, 14.452038764954, 4381.8002929688)
                elseif Lv == 90 or Lv <= 99 or SelectMonster == "Snow Bandit [Lv. 90]" then -- Snow Bandit
                    Ms = "Snow Bandit [Lv. 90]"
                    NameQuest = "SnowQuest"
                    QuestLv = 1
                    NameMon = "Snow Bandit"
                    CFrameQ = CFrame.new(1386.8073730469, 87.272789001465, -1298.3576660156)
                    CFrameMon = CFrame.new(1356.3028564453, 105.76865386963, -1328.2418212891)
                elseif Lv == 100 or Lv <= 119 or SelectMonster == "Snowman [Lv. 100]" then -- Snowman
                    Ms = "Snowman [Lv. 100]"
                    NameQuest = "SnowQuest"
                    QuestLv = 2
                    NameMon = "Snowman"
                    CFrameQ = CFrame.new(1386.8073730469, 87.272789001465, -1298.3576660156)
                    CFrameMon = CFrame.new(1218.7956542969, 138.01184082031, -1488.0262451172)
                elseif Lv == 120 or Lv <= 149 or SelectMonster == "Chief Petty Officer [Lv. 120]" then -- Chief Petty Officer
                    Ms = "Chief Petty Officer [Lv. 120]"
                    NameQuest = "MarineQuest2"
                    QuestLv = 1
                    NameMon = "Chief Petty Officer"
                    CFrameQ = CFrame.new(-5035.49609375, 28.677835464478, 4324.1840820313)
                    CFrameMon = CFrame.new(-4931.1552734375, 65.793113708496, 4121.8393554688)
                elseif Lv == 150 or Lv <= 174 or SelectMonster == "Sky Bandit [Lv. 150]" then -- Sky Bandit
                    Ms = "Sky Bandit [Lv. 150]"
                    NameQuest = "SkyQuest"
                    QuestLv = 1
                    NameMon = "Sky Bandits"
                    CFrameQ = CFrame.new(-4842.1372070313, 717.69543457031, -2623.0483398438)
                    CFrameMon = CFrame.new(-4955.6411132813, 365.46365356445, -2908.1865234375)
                elseif Lv == 175 or Lv <= 249 or SelectMonster == "Dark Master [Lv. 175]" then -- Dark Master
                    Ms = "Dark Master [Lv. 175]"
                    NameQuest = "SkyQuest"
                    QuestLv = 2
                    NameMon = "Dark Master"
                    CFrameQ = CFrame.new(-4842.1372070313, 717.69543457031, -2623.0483398438)
                    CFrameMon = CFrame.new(-5148.1650390625, 439.04571533203, -2332.9611816406)
                elseif Lv == 250 or Lv <= 274 or SelectMonster == "Toga Warrior [Lv. 250]" then -- Toga Warrior
                    Ms = "Toga Warrior [Lv. 250]"
                    NameQuest = "ColosseumQuest"
                    QuestLv = 1
                    NameMon = "Toga Warrior"
                    CFrameQ = CFrame.new(-1577.7890625, 7.4151420593262, -2984.4838867188)
                    CFrameMon = CFrame.new(-1872.5166015625, 49.080215454102, -2913.810546875)
                elseif Lv == 275 or Lv <= 299 or SelectMonster == "Gladiator [Lv. 275]" then -- Gladiator
                    Ms = "Gladiator [Lv. 275]"
                    NameQuest = "ColosseumQuest"
                    QuestLv = 2
                    NameMon = "Gladiator"
                    CFrameQ = CFrame.new(-1577.7890625, 7.4151420593262, -2984.4838867188)
                    CFrameMon = CFrame.new(-1521.3740234375, 81.203170776367, -3066.3139648438)
                elseif Lv == 300 or Lv <= 329 or SelectMonster == "Military Soldier [Lv. 300]" then -- Military Soldier
                    Ms = "Military Soldier [Lv. 300]"
                    NameQuest = "MagmaQuest"
                    QuestLv = 1
                    NameMon = "Military Soldier"
                    CFrameQ = CFrame.new(-5316.1157226563, 12.262831687927, 8517.00390625)
                    CFrameMon = CFrame.new(-5369.0004882813, 61.24352645874, 8556.4921875)
                elseif Lv == 330 or Lv <= 374 or SelectMonster == "Military Spy [Lv. 325]" then -- Military Spy
                    Ms = "Military Spy [Lv. 325]"
                    NameQuest = "MagmaQuest"
                    QuestLv = 2
                    NameMon = "Military Spy"
                    CFrameQ = CFrame.new(-5316.1157226563, 12.262831687927, 8517.00390625)
                    CFrameMon = CFrame.new(-5984.0532226563, 82.14656829834, 8753.326171875)
                elseif Lv == 375 or Lv <= 399 or SelectMonster == "Fishman Warrior [Lv. 375]" then -- Fishman Warrior 
                    _G.FM = true
                    Ms = "Fishman Warrior [Lv. 375]"
                    NameQuest = "FishmanQuest"
                    QuestLv = 1
                    NameMon = "Fishman Warrior"
                    CFrameQ = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
                    CFrameMon = CFrame.new(60844.10546875, 98.462875366211, 1298.3985595703)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
                    end
                elseif Lv == 400 or Lv <= 449 or SelectMonster == "Fishman Commando [Lv. 400]" then -- Fishman Commando
                    _G.FM = true
                    Ms = "Fishman Commando [Lv. 400]"
                    NameQuest = "FishmanQuest"
                    QuestLv = 2
                    NameMon = "Fishman Commando"
                    CFrameQ = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
                    CFrameMon = CFrame.new(61738.3984375, 64.207321166992, 1433.8375244141)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
                    end
                elseif Lv == 450 or Lv <= 474 or SelectMonster == "God's Guard [Lv. 450]" then -- God's Guard
                    _G.FM = false
                    Ms = "God's Guard [Lv. 450]"
                    NameQuest = "SkyExp1Quest"
                    QuestLv = 1
                    NameMon = "God's Guard"
                    CFrameQ = CFrame.new(-4721.8603515625, 845.30297851563, -1953.8489990234)
                    CFrameMon = CFrame.new(-4628.0498046875, 866.92877197266, -1931.2352294922)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
                    end
                elseif Lv == 475 or Lv <= 524 or SelectMonster == "Shanda [Lv. 475]" then -- Shanda
                    _G.FM = false
                    Ms = "Shanda [Lv. 475]"
                    NameQuest = "SkyExp1Quest"
                    QuestLv = 2
                    NameMon = "Shanda"
                    CFrameQ = CFrame.new(-7863.1596679688, 5545.5190429688, -378.42266845703)
                    CFrameMon = CFrame.new(-7685.1474609375, 5601.0751953125, -441.38876342773)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
                    end
                elseif Lv == 525 or Lv <= 549 or SelectMonster == "Royal Squad [Lv. 525]" then -- Royal Squad
                    Ms = "Royal Squad [Lv. 525]"
                    NameQuest = "SkyExp2Quest"
                    QuestLv = 1
                    NameMon = "Royal Squad"
                    CFrameQ = CFrame.new(-7903.3828125, 5635.9897460938, -1410.923828125)
                    CFrameMon = CFrame.new(-7654.2514648438, 5637.1079101563, -1407.7550048828)
                elseif Lv == 550 or Lv <= 624 or SelectMonster == "Royal Soldier [Lv. 550]" then -- Royal Soldier
                    Ms = "Royal Soldier [Lv. 550]"
                    NameQuest = "SkyExp2Quest"
                    QuestLv = 2
                    NameMon = "Royal Soldier"
                    CFrameQ = CFrame.new(-7903.3828125, 5635.9897460938, -1410.923828125)
                    CFrameMon = CFrame.new(-7760.4106445313, 5679.9077148438, -1884.8112792969)
                elseif Lv == 625 or Lv <= 649 or SelectMonster == "Galley Pirate [Lv. 625]" then -- Galley Pirate
                    Ms = "Galley Pirate [Lv. 625]"
                    NameQuest = "FountainQuest"
                    QuestLv = 1
                    NameMon = "Galley Pirate"
                    CFrameQ = CFrame.new(5258.2788085938, 38.526931762695, 4050.044921875)
                    CFrameMon = CFrame.new(5557.1684570313, 152.32717895508, 3998.7758789063)
                elseif Lv >= 650 or SelectMonster == "Galley Captain [Lv. 650]" then -- Galley Captain
                    Ms = "Galley Captain [Lv. 650]"
                    NameQuest = "FountainQuest"
                    QuestLv = 2
                    NameMon = "Galley Captain"
                    CFrameQ = CFrame.new(5258.2788085938, 38.526931762695, 4050.044921875)
                    CFrameMon = CFrame.new(5677.6772460938, 92.786109924316, 4966.6323242188)
                end
            end
            if New_World then
                if Lv == 700 or Lv <= 724 or SelectMonster == "Raider [Lv. 700]" then -- Raider
                    Ms = "Raider [Lv. 700]"
                    NameQuest = "Area1Quest"
                    QuestLv = 1
                    NameMon = "Raider"
                    CFrameQ = CFrame.new(-427.72567749023, 72.99634552002, 1835.9426269531)
                    CFrameMon = CFrame.new(68.874565124512, 93.635643005371, 2429.6752929688)
                elseif Lv == 725 or Lv <= 774 or SelectMonster == "Mercenary [Lv. 725]" then -- Mercenary
                    Ms = "Mercenary [Lv. 725]"
                    NameQuest = "Area1Quest"
                    QuestLv = 2
                    NameMon = "Mercenary"
                    CFrameQ = CFrame.new(-427.72567749023, 72.99634552002, 1835.9426269531)
                    CFrameMon = CFrame.new(-864.85009765625, 122.47104644775, 1453.1505126953)
                elseif Lv == 775 or Lv <= 799 or SelectMonster == "Swan Pirate [Lv. 775]" then -- Swan Pirate
                    Ms = "Swan Pirate [Lv. 775]"
                    NameQuest = "Area2Quest"
                    QuestLv = 1
                    NameMon = "Swan Pirate"
                    CFrameQ = CFrame.new(635.61151123047, 73.096351623535, 917.81298828125)
                    CFrameMon = CFrame.new(1065.3669433594, 137.64012145996, 1324.3798828125)
                elseif Lv == 800 or Lv <= 874 or SelectMonster == "Factory Staff [Lv. 800]" then -- Factory Staff
                    Ms = "Factory Staff [Lv. 800]"
                    NameQuest = "Area2Quest"
                    QuestLv = 2
                    NameMon = "Factory Staff"
                    CFrameQ = CFrame.new(635.61151123047, 73.096351623535, 917.81298828125)
                    CFrameMon = CFrame.new(533.22045898438, 128.46876525879, 355.62615966797)
                elseif Lv == 875 or Lv <= 899 or SelectMonster == "Marine Lieutenant [Lv. 875]" then -- Marine Lieutenant
                    Ms = "Marine Lieutenant [Lv. 875]"
                    NameQuest = "MarineQuest3"
                    QuestLv = 1
                    NameMon = "Marine Lieutenant"
                    CFrameQ = CFrame.new(-2440.9934082031, 73.04190826416, -3217.7082519531)
                    CFrameMon = CFrame.new(-2489.2622070313, 84.613594055176, -3151.8830566406)
                elseif Lv == 900 or Lv <= 949 or SelectMonster == "Marine Captain [Lv. 900]" then -- Marine Captain
                    Ms = "Marine Captain [Lv. 900]"
                    NameQuest = "MarineQuest3"
                    QuestLv = 2
                    NameMon = "Marine Captain"
                    CFrameQ = CFrame.new(-2440.9934082031, 73.04190826416, -3217.7082519531)
                    CFrameMon = CFrame.new(-2335.2026367188, 79.786659240723, -3245.8674316406)
                elseif Lv == 950 or Lv <= 974 or SelectMonster == "Zombie [Lv. 950]" then -- Zombie
                    Ms = "Zombie [Lv. 950]"
                    NameQuest = "ZombieQuest"
                    QuestLv = 1
                    NameMon = "Zombie"
                    CFrameQ = CFrame.new(-5494.3413085938, 48.505931854248, -794.59094238281)
                    CFrameMon = CFrame.new(-5536.4970703125, 101.08577728271, -835.59075927734)
                elseif Lv == 975 or Lv <= 999 or SelectMonster == "Vampire [Lv. 975]" then -- Vampire
                    Ms = "Vampire [Lv. 975]"
                    NameQuest = "ZombieQuest"
                    QuestLv = 2
                    NameMon = "Vampire"
                    CFrameQ = CFrame.new(-5494.3413085938, 48.505931854248, -794.59094238281)
                    CFrameMon = CFrame.new(-5806.1098632813, 16.722528457642, -1164.4384765625)
                elseif Lv == 1000 or Lv <= 1049 or SelectMonster == "Snow Trooper [Lv. 1000]" then -- Snow Trooper
                    Ms = "Snow Trooper [Lv. 1000]"
                    NameQuest = "SnowMountainQuest"
                    QuestLv = 1
                    NameMon = "Snow Trooper"
                    CFrameQ = CFrame.new(607.05963134766, 401.44781494141, -5370.5546875)
                    CFrameMon = CFrame.new(535.21051025391, 432.74209594727, -5484.9165039063)
                elseif Lv == 1050 or Lv <= 1099 or SelectMonster == "Winter Warrior [Lv. 1050]" then -- Winter Warrior
                    Ms = "Winter Warrior [Lv. 1050]"
                    NameQuest = "SnowMountainQuest"
                    QuestLv = 2
                    NameMon = "Winter Warrior"
                    CFrameQ = CFrame.new(607.05963134766, 401.44781494141, -5370.5546875)
                    CFrameMon = CFrame.new(1234.4449462891, 456.95419311523, -5174.130859375)
                elseif Lv == 1100 or Lv <= 1124 or SelectMonster == "Lab Subordinate [Lv. 1100]" then -- Lab Subordinate
                    Ms = "Lab Subordinate [Lv. 1100]"
                    NameQuest = "IceSideQuest"
                    QuestLv = 1
                    NameMon = "Lab Subordinate"
                    CFrameQ = CFrame.new(-6061.841796875, 15.926671981812, -4902.0385742188)
                    CFrameMon = CFrame.new(-5720.5576171875, 63.309471130371, -4784.6103515625)
                elseif Lv == 1125 or Lv <= 1174 or SelectMonster == "Horned Warrior [Lv. 1125]" then -- Horned Warrior
                    Ms = "Horned Warrior [Lv. 1125]"
                    NameQuest = "IceSideQuest"
                    QuestLv = 2
                    NameMon = "Horned Warrior"
                    CFrameQ = CFrame.new(-6061.841796875, 15.926671981812, -4902.0385742188)
                    CFrameMon = CFrame.new(-6292.751953125, 91.181983947754, -5502.6499023438)
                elseif Lv == 1175 or Lv <= 1199 or SelectMonster == "Magma Ninja [Lv. 1175]" then -- Magma Ninja
                    Ms = "Magma Ninja [Lv. 1175]"
                    NameQuest = "FireSideQuest"
                    QuestLv = 1
                    NameMon = "Magma Ninja"
                    CFrameQ = CFrame.new(-5429.0473632813, 15.977565765381, -5297.9614257813)
                    CFrameMon = CFrame.new(-5461.8388671875, 130.36347961426, -5836.4702148438)
                elseif Lv == 1200 or Lv <= 1249 or SelectMonster == "Lava Pirate [Lv. 1200]" then -- Lava Pirate
                    Ms = "Lava Pirate [Lv. 1200]"
                    NameQuest = "FireSideQuest"
                    QuestLv = 2
                    NameMon = "Lava Pirate"
                    CFrameQ = CFrame.new(-5429.0473632813, 15.977565765381, -5297.9614257813)
                    CFrameMon = CFrame.new(-5251.1889648438, 55.164535522461, -4774.4096679688)
                elseif Lv == 1250 or Lv <= 1274 or SelectMonster == "Ship Deckhand [Lv. 1250]" then -- Ship Deckhand
                    Ms = "Ship Deckhand [Lv. 1250]"
                    NameQuest = "ShipQuest1"
                    QuestLv = 1
                    NameMon = "Ship Deckhand"
                    CFrameQ = CFrame.new(1040.2927246094, 125.08293151855, 32911.0390625)
                    CFrameMon = CFrame.new(921.12365722656, 125.9839553833, 33088.328125)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                    end
                elseif Lv == 1275 or Lv <= 1299 or SelectMonster == "Ship Engineer [Lv. 1275]" then -- Ship Engineer
                    Ms = "Ship Engineer [Lv. 1275]"
                    NameQuest = "ShipQuest1"
                    QuestLv = 2
                    NameMon = "Ship Engineer"
                    CFrameQ = CFrame.new(1040.2927246094, 125.08293151855, 32911.0390625)
                    CFrameMon = CFrame.new(886.28179931641, 40.47790145874, 32800.83203125)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                    end
                elseif Lv == 1300 or Lv <= 1324 or SelectMonster == "Ship Steward [Lv. 1300]" then -- Ship Steward
                    Ms = "Ship Steward [Lv. 1300]"
                    NameQuest = "ShipQuest2"
                    QuestLv = 1
                    NameMon = "Ship Steward"
                    CFrameQ = CFrame.new(971.42065429688, 125.08293151855, 33245.54296875)
                    CFrameMon = CFrame.new(943.85504150391, 129.58183288574, 33444.3671875)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                    end
                elseif Lv == 1325 or Lv <= 1349 or SelectMonster == "Ship Officer [Lv. 1325]" then -- Ship Officer
                    Ms = "Ship Officer [Lv. 1325]"
                    NameQuest = "ShipQuest2"
                    QuestLv = 2
                    NameMon = "Ship Officer"
                    CFrameQ = CFrame.new(971.42065429688, 125.08293151855, 33245.54296875)
                    CFrameMon = CFrame.new(955.38458251953, 181.08335876465, 33331.890625)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                    end
                elseif Lv == 1350 or Lv <= 1374 or SelectMonster == "Arctic Warrior [Lv. 1350]" then -- Arctic Warrior
                    Ms = "Arctic Warrior [Lv. 1350]"
                    NameQuest = "FrostQuest"
                    QuestLv = 1
                    NameMon = "Arctic Warrior"
                    CFrameQ = CFrame.new(5668.1372070313, 28.202531814575, -6484.6005859375)
                    CFrameMon = CFrame.new(5935.4541015625, 77.26016998291, -6472.7568359375)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
                    end
                elseif Lv == 1375 or Lv <= 1424 or SelectMonster == "Snow Lurker [Lv. 1375]" then -- Snow Lurker
                    Ms = "Snow Lurker [Lv. 1375]"
                    NameQuest = "FrostQuest"
                    QuestLv = 2
                    NameMon = "Snow Lurker"
                    CFrameQ = CFrame.new(5668.1372070313, 28.202531814575, -6484.6005859375)
                    CFrameMon = CFrame.new(5628.482421875, 57.574996948242, -6618.3481445313)
                elseif Lv == 1425 or Lv <= 1449 or SelectMonster == "Sea Soldier [Lv. 1425]" then -- Sea Soldier
                    Ms = "Sea Soldier [Lv. 1425]"
                    NameQuest = "ForgottenQuest"
                    QuestLv = 1
                    NameMon = "Sea Soldier"
                    CFrameQ = CFrame.new(-3054.5827636719, 236.87213134766, -10147.790039063)
                    CFrameMon = CFrame.new(-3185.0153808594, 58.789089202881, -9663.6064453125)
                elseif Lv >= 1450 or SelectMonster == "Water Fighter [Lv. 1450]" then -- Water Fighter
                    Ms = "Water Fighter [Lv. 1450]"
                    NameQuest = "ForgottenQuest"
                    QuestLv = 2
                    NameMon = "Water Fighter"
                    CFrameQ = CFrame.new(-3054.5827636719, 236.87213134766, -10147.790039063)
                    CFrameMon = CFrame.new(-3262.9301757813, 298.69036865234, -10552.529296875)
                end
            end
            if Three_World then
                if Lv == 1500 or Lv <= 1524 or SelectMonster == "Pirate Millionaire [Lv. 1500]" then -- Pirate Millionaire
                    Ms = "Pirate Millionaire [Lv. 1500]"
                    NameQuest = "PiratePortQuest"
                    QuestLv = 1
                    NameMon = "Pirate Millionaire"
                    CFrameQ = CFrame.new(-289.61752319336, 43.819011688232, 5580.0903320313)
                    CFrameMon = CFrame.new(-435.68109130859, 189.69866943359, 5551.0756835938)
                elseif Lv == 1525 or Lv <= 1574 or SelectMonster == "Pistol Billionaire [Lv. 1525]" then -- Pistol Billoonaire
                    Ms = "Pistol Billionaire [Lv. 1525]"
                    NameQuest = "PiratePortQuest"
                    QuestLv = 2
                    NameMon = "Pistol Billionaire"
                    CFrameQ = CFrame.new(-289.61752319336, 43.819011688232, 5580.0903320313)
                    CFrameMon = CFrame.new(-236.53652954102, 217.46676635742, 6006.0883789063)
                elseif Lv == 1575 or Lv <= 1599 or SelectMonster == "Dragon Crew Warrior [Lv. 1575]" then -- Dragon Crew Warrior
                    Ms = "Dragon Crew Warrior [Lv. 1575]"
                    NameQuest = "AmazonQuest"
                    QuestLv = 1
                    NameMon = "Dragon Crew Warrior"
                    CFrameQ = CFrame.new(5833.1147460938, 51.60498046875, -1103.0693359375)
                    CFrameMon = CFrame.new(6301.9975585938, 104.77153015137, -1082.6075439453)
                elseif Lv == 1600 or Lv <= 1624 or SelectMonster == "Dragon Crew Archer [Lv. 1600]" then -- Dragon Crew Archer
                    Ms = "Dragon Crew Archer [Lv. 1600]"
                    NameQuest = "AmazonQuest"
                    QuestLv = 2
                    NameMon = "Dragon Crew Archer"
                    CFrameQ = CFrame.new(5833.1147460938, 51.60498046875, -1103.0693359375)
                    CFrameMon = CFrame.new(6831.1171875, 441.76708984375, 446.58615112305)
                elseif Lv == 1625 or Lv <= 1649 or SelectMonster == "Female Islander [Lv. 1625]" then -- Female Islander
                    Ms = "Female Islander [Lv. 1625]"
                    NameQuest = "AmazonQuest2"
                    QuestLv = 1
                    NameMon = "Female Islander"
                    CFrameQ = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
                    CFrameMon = CFrame.new(5792.5166015625, 848.14392089844, 1084.1818847656)
                elseif Lv == 1650 or Lv <= 1699 or SelectMonster == "Giant Islander [Lv. 1650]" then -- Giant Islander
                    Ms = "Giant Islander [Lv. 1650]"
                    NameQuest = "AmazonQuest2"
                    QuestLv = 2
                    NameMon = "Giant Islander"
                    CFrameQ = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
                    CFrameMon = CFrame.new(5009.5068359375, 664.11071777344, -40.960144042969)
                elseif Lv == 1700 or Lv <= 1724 or SelectMonster == "Marine Commodore [Lv. 1700]" then -- Marine Commodore
                    Ms = "Marine Commodore [Lv. 1700]"
                    NameQuest = "MarineTreeIsland"
                    QuestLv = 1
                    NameMon = "Marine Commodore"
                    CFrameQ = CFrame.new(2179.98828125, 28.731239318848, -6740.0551757813)
                    CFrameMon = CFrame.new(2198.0063476563, 128.71075439453, -7109.5043945313)
                elseif Lv == 1725 or Lv <= 1774 or SelectMonster == "Marine Rear Admiral [Lv. 1725]" then -- Marine Rear Admiral
                    Ms = "Marine Rear Admiral [Lv. 1725]"
                    NameQuest = "MarineTreeIsland"
                    QuestLv = 2
                    NameMon = "Marine Rear Admiral"
                    CFrameQ = CFrame.new(2179.98828125, 28.731239318848, -6740.0551757813)
                    CFrameMon = CFrame.new(3294.3142089844, 385.41125488281, -7048.6342773438)
                elseif Lv == 1775 or Lv <= 1799 or SelectMonster == "Fishman Raider [Lv. 1775]" then -- Fishman Raide
                    Ms = "Fishman Raider [Lv. 1775]"
                    NameQuest = "DeepForestIsland3"
                    QuestLv = 1
                    NameMon = "Fishman Raider"
                    CFrameQ = CFrame.new(-10582.759765625, 331.78845214844, -8757.666015625)
                    CFrameMon = CFrame.new(-10553.268554688, 521.38439941406, -8176.9458007813)
                elseif Lv == 1800 or Lv <= 1824 or SelectMonster == "Fishman Captain [Lv. 1800]" then -- Fishman Captain
                    Ms = "Fishman Captain [Lv. 1800]"
                    NameQuest = "DeepForestIsland3"
                    QuestLv = 2
                    NameMon = "Fishman Captain"
                    CFrameQ = CFrame.new(-10583.099609375, 331.78845214844, -8759.4638671875)
                    CFrameMon = CFrame.new(-10789.401367188, 427.18637084961, -9131.4423828125)
                elseif Lv == 1825 or Lv <= 1849 or SelectMonster == "Forest Pirate [Lv. 1825]" then -- Forest Pirate
                    Ms = "Forest Pirate [Lv. 1825]"
                    NameQuest = "DeepForestIsland"
                    QuestLv = 1
                    NameMon = "Forest Pirate"
                    CFrameQ = CFrame.new(-13232.662109375, 332.40396118164, -7626.4819335938)
                    CFrameMon = CFrame.new(-13489.397460938, 400.30349731445, -7770.251953125)
                elseif Lv == 1850 or Lv <= 1899 or SelectMonster == "Mythological Pirate [Lv. 1850]" then -- Mythological Pirate
                    Ms = "Mythological Pirate [Lv. 1850]"
                    NameQuest = "DeepForestIsland"
                    QuestLv = 2
                    NameMon = "Mythological Pirate"
                    CFrameQ = CFrame.new(-13232.662109375, 332.40396118164, -7626.4819335938)
                    CFrameMon = CFrame.new(-13508.616210938, 582.46228027344, -6985.3037109375)
                elseif Lv >= 1900 and Lv <= 1924 or SelectMonster == "Jungle Pirate [Lv. 1900]" then -- Jungle Pirate
                    Ms = "Jungle Pirate [Lv. 1900]"
                    NameQuest = "DeepForestIsland2"
                    QuestLv = 1
                    NameMon = "Jungle Pirate"
                    CFrameQ = CFrame.new(-12682.096679688, 390.88653564453, -9902.1240234375)
                    CFrameMon = CFrame.new(-12267.103515625, 459.75262451172, -10277.200195313)
                elseif Lv >= 1925 and Lv <= 1974 or SelectMonster == "Musketeer Pirate [Lv. 1925]" then -- Musketeer Pirate
                    Ms = "Musketeer Pirate [Lv. 1925]"
                    NameQuest = "DeepForestIsland2"
                    QuestLv = 2
                    NameMon = "Musketeer Pirate"
                    CFrameQ = CFrame.new(-12682.096679688, 390.88653564453, -9902.1240234375)
                    CFrameMon = CFrame.new(-13291.5078125, 520.47338867188, -9904.638671875)
                elseif Lv >= 1975 and Lv <= 1999 or SelectMonster == "Musketeer Pirate [Lv. 1925]" then -- Reborn Skeleton
                    Ms = "Musketeer Pirate [Lv. 1925]"
                    NameQuest = "DeepForestIsland2"
                    QuestLv = 2
                    NameMon = "Musketeer Pirate"
                    CFrameQ = CFrame.new(-12682.096679688, 390.88653564453, -9902.1240234375)
                    CFrameMon = CFrame.new(-13291.5078125, 520.47338867188, -9904.638671875)
                elseif Lv >= 2000 and Lv <= 2024 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Living Zombie
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2025 and Lv <= 2049 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Demonic Soul
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2050 and Lv <= 2074 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Posessed Mummy
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2075 and Lv <= 2099 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Peanut Scout
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2100 and Lv <= 2124 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Peanut President
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2125 and Lv <= 2149 or SelectMonster == "Living Zombie [Lv. 2000]" then --Ice Cream Chef
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2150 and Lv <= 2200 or SelectMonster == "Ice Cream Commander [Lv. 2150]" then -- Ice Cream Commander
                    Ms = "Ice Cream Commander [Lv. 2150]"
                    NameQuest = "IceCreamIslandQuest"
                    QuestLv = 2
                    NameMon = "Ice Cream Commanders"
                    CFrameQ = CFrame.new(-821.35913085938, 65.845329284668, -10965.2578125)
                    CFrameMon = CFrame.new(-697.65338134766, 174.48368835449, -11218.38671875)
                elseif Lv >= 2200 and Lv <= 2250 or SelectMonster == "Ice Cream Commander [Lv. 2150]" then -- Ice Cream Commander
                    Ms = "Cookie Crafter [Lv. 2200]"
                    NameQuest = "CakeQuest1"
                    QuestLv = 1
                    NameMon = "Cookie Crafters"
                    CFrameQ = CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)
                    CFrameMon = CFrame.new(-2358.5791015625, 36.85615539550781, -12111.052734375)
                elseif Lv >= 2225 or SelectMonster == "Cake Guard [Lv. 2225]" then
                    Ms = "Cake Guard [Lv. 2225]"
                    NameQuest = "CakeQuest1"
                    QuestLv = 2
                    NameMon = "Cake Guards"
                    CFrameMon = CFrame.new(-1430.4925537109375, 36.85621643066406, -12322.162109375)
                    CFrameQ = CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)
                end
            end
        end
    
        function CheckQuestBoss()
        -- Old World
            if _G.SelectBoss == "Saber Expert [Lv. 200] [Boss]" then
                MsBoss = "Saber Expert [Lv. 200] [Boss]"
                NameBoss = "Saber Expert"
                CFrameBoss = CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094)
            elseif _G.SelectBoss == "The Saw [Lv. 100] [Boss]" then
                MsBoss = "The Saw [Lv. 100] [Boss]"
                NameBoss = "The Saw"
                CFrameBoss = CFrame.new(-683.519897, 13.8534927, 1610.87854, -0.290192783, 6.88365773e-08, 0.956968188, 6.98413629e-08, 1, -5.07531119e-08, -0.956968188, 5.21077759e-08, -0.290192783)
            elseif _G.SelectBoss == "Greybeard [Lv. 750] [Raid Boss]" then
                MsBoss = "Greybeard [Lv. 750] [Raid Boss]"
                NameBoss = "Greybeard"
                CFrameBoss = CFrame.new(-4955.72949, 80.8163834, 4305.82666, -0.433646321, -1.03394289e-08, 0.901083171, -3.0443168e-08, 1, -3.17633075e-09, -0.901083171, -2.88092288e-08, -0.433646321)
            elseif _G.SelectBoss == "The Gorilla King [Lv. 25] [Boss]" then
                MsBoss = "The Gorilla King [Lv. 25] [Boss]"
                NameBoss = "The Gorilla King"
                NameQuestBoss = "JungleQuest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
                CFrameBoss = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
            elseif _G.SelectBoss == "Bobby [Lv. 55] [Boss]" then
                MsBoss = "Bobby [Lv. 55] [Boss]"
                NameBoss = "Bobby"
                NameQuestBoss = "BuggyQuest1"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
                CFrameBoss = CFrame.new(-1147.65173, 32.5966301, 4156.02588, 0.956680477, -1.77109952e-10, -0.29113996, 5.16530874e-10, 1, 1.08897802e-09, 0.29113996, -1.19218679e-09, 0.956680477)
            elseif _G.SelectBoss == "Yeti [Lv. 110] [Boss]" then
                MsBoss = "Yeti [Lv. 110] [Boss]"
                NameBoss = "Yeti"
                NameQuestBoss = "SnowQuest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(1384.90247, 87.3078308, -1296.6825, 0.280209213, 2.72035177e-08, -0.959938943, -6.75690828e-08, 1, 8.6151708e-09, 0.959938943, 6.24481444e-08, 0.280209213)
                CFrameBoss = CFrame.new(1221.7356, 138.046906, -1488.84082, 0.349343032, -9.49245944e-08, 0.936994851, 6.29478194e-08, 1, 7.7838429e-08, -0.936994851, 3.17894653e-08, 0.349343032)
            elseif _G.SelectBoss == "Mob Leader [Lv. 120] [Boss]" then
                MsBoss = "Mob Leader [Lv. 120] [Boss]"
                NameBoss = "Mob Leader"
                CFrameBoss = CFrame.new(-2848.59399, 7.4272871, 5342.44043, -0.928248107, -8.7248246e-08, 0.371961564, -7.61816636e-08, 1, 4.44474857e-08, -0.371961564, 1.29216433e-08, -0.92824)
            elseif _G.SelectBoss == "Vice Admiral [Lv. 130] [Boss]" then
                MsBoss = "Vice Admiral [Lv. 130] [Boss]"
                NameBoss = "Vice Admiral"
                NameQuestBoss = "MarineQuest2"
                LevelQuestBoss = 2
                CFrameQuestBoss = CFrame.new(-5035.42285, 28.6520386, 4324.50293, -0.0611100644, -8.08395768e-08, 0.998130739, -1.57416586e-08, 1, 8.00271849e-08, -0.998130739, -1.08217701e-08, -0.0611100644)
                CFrameBoss = CFrame.new(-5078.45898, 99.6520691, 4402.1665, -0.555574954, -9.88630566e-11, 0.831466436, -6.35508286e-08, 1, -4.23449258e-08, -0.831466436, -7.63661632e-08, -0.555574954)
            elseif _G.SelectBoss == "Warden [Lv. 175] [Boss]" then
                MsBoss = "Warden [Lv. 175] [Boss]"
                NameBoss = "Warden"
                NameQuestBoss = "ImpelQuest"
                LevelQuestBoss = 1
                CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
                CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
            elseif _G.SelectBoss == "Chief Warden [Lv. 200] [Boss]" then
                MsBoss = "Chief Warden [Lv. 200] [Boss]"
                NameBoss = "Chief Warden"
                NameQuestBoss = "ImpelQuest"
                LevelQuestBoss = 2
                CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
                CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
            elseif _G.SelectBoss == "Swan [Lv. 225] [Boss]" then
                MsBoss = "Swan [Lv. 225] [Boss]"
                NameBoss = "Swan"
                NameQuestBoss = "ImpelQuest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
                CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
            elseif _G.SelectBoss == "Magma Admiral [Lv. 350] [Boss]" then
                MsBoss = "Magma Admiral [Lv. 350] [Boss]"
                NameBoss = "Magma Admiral"
                NameQuestBoss = "MagmaQuest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-5317.07666, 12.2721891, 8517.41699, 0.51175487, -2.65508806e-08, -0.859131515, -3.91131572e-08, 1, -5.42026761e-08, 0.859131515, 6.13418294e-08, 0.51175487)
                CFrameBoss = CFrame.new(-5530.12646, 22.8769703, 8859.91309, 0.857838571, 2.23414389e-08, 0.513919294, 1.53689133e-08, 1, -6.91265853e-08, -0.513919294, 6.71978384e-08, 0.857838571)
            elseif _G.SelectBoss == "Fishman Lord [Lv. 425] [Boss]" then
                MsBoss = "Fishman Lord [Lv. 425] [Boss]"
                NameBoss = "Fishman Lord"
                NameQuestBoss = "FishmanQuest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(61123.0859, 18.5066795, 1570.18018, 0.927145958, 1.0624845e-07, 0.374700129, -6.98219367e-08, 1, -1.10790765e-07, -0.374700129, 7.65569368e-08, 0.927145958)
                CFrameBoss = CFrame.new(61351.7773, 31.0306778, 1113.31409, 0.999974668, 0, -0.00714713801, 0, 1.00000012, 0, 0.00714714266, 0, 0.999974549)
            elseif _G.SelectBoss == "Wysper [Lv. 500] [Boss]" then
                MsBoss = "Wysper [Lv. 500] [Boss]"
                NameBoss = "Wysper"
                NameQuestBoss = "SkyExp1Quest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-7862.94629, 5545.52832, -379.833954, 0.462944925, 1.45838088e-08, -0.886386991, 1.0534996e-08, 1, 2.19553424e-08, 0.886386991, -1.95022007e-08, 0.462944925)
                CFrameBoss = CFrame.new(-7925.48389, 5550.76074, -636.178345, 0.716468513, -1.22915289e-09, 0.697619379, 3.37381434e-09, 1, -1.70304748e-09, -0.697619379, 3.57381835e-09, 0.716468513)
            elseif _G.SelectBoss == "Thunder God [Lv. 575] [Boss]" then
                MsBoss = "Thunder God [Lv. 575] [Boss]"
                NameBoss = "Thunder God"
                NameQuestBoss = "SkyExp2Quest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-7902.78613, 5635.99902, -1411.98706, -0.0361216255, -1.16895912e-07, 0.999347389, 1.44533963e-09, 1, 1.17024491e-07, -0.999347389, 5.6715117e-09, -0.0361216255)
                CFrameBoss = CFrame.new(-7917.53613, 5616.61377, -2277.78564, 0.965189934, 4.80563429e-08, -0.261550069, -6.73089886e-08, 1, -6.46515304e-08, 0.261550069, 8.00056768e-08, 0.965189934)
            elseif _G.SelectBoss == "Cyborg [Lv. 675] [Boss]" then
                MsBoss = "Cyborg [Lv. 675] [Boss]"
                NameBoss = "Cyborg"
                NameQuestBoss = "FountainQuest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(5253.54834, 38.5361786, 4050.45166, -0.0112687312, -9.93677887e-08, -0.999936521, 2.55291371e-10, 1, -9.93769547e-08, 0.999936521, -1.37512213e-09, -0.0112687312)
                CFrameBoss = CFrame.new(6041.82813, 52.7112198, 3907.45142, -0.563162148, 1.73805248e-09, -0.826346457, -5.94632716e-08, 1, 4.26280238e-08, 0.826346457, 7.31437524e-08, -0.563162148)
            -- New World
            elseif _G.SelectBoss == "Diamond [Lv. 750] [Boss]" then
                MsBoss = "Diamond [Lv. 750] [Boss]"
                NameBoss = "Diamond"
                NameQuestBoss = "Area1Quest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
                CFrameBoss = CFrame.new(-1736.26587, 198.627731, -236.412857, -0.997808516, 0, -0.0661673471, 0, 1, 0, 0.0661673471, 0, -0.997808516)
            elseif _G.SelectBoss == "Jeremy [Lv. 850] [Boss]" then
                MsBoss = "Jeremy [Lv. 850] [Boss]"
                NameBoss = "Jeremy"
                NameQuestBoss = "Area2Quest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
                CFrameBoss = CFrame.new(2203.76953, 448.966034, 752.731079, -0.0217453763, 0, -0.999763548, 0, 1, 0, 0.999763548, 0, -0.0217453763)
            elseif _G.SelectBoss == "Fajita [Lv. 925] [Boss]" then
                MsBoss = "Fajita [Lv. 925] [Boss]"
                NameBoss = "Fajita"
                NameQuestBoss = "MarineQuest3"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
                CFrameBoss = CFrame.new(-2297.40332, 115.449463, -3946.53833, 0.961227536, -1.46645796e-09, -0.275756449, -2.3212845e-09, 1, -1.34094433e-08, 0.275756449, 1.35296352e-08, 0.961227536)
            elseif _G.SelectBoss == "Don Swan [Lv. 1000] [Boss]" then
                MsBoss = "Don Swan [Lv. 1000] [Boss]"
                NameBoss = "Don Swan"
                CFrameBoss = CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072)
            elseif _G.SelectBoss == "Smoke Admiral [Lv. 1150] [Boss]" then
                MsBoss = "Smoke Admiral [Lv. 1150] [Boss]"
                NameBoss = "Smoke Admiral"
                NameQuestBoss = "IceSideQuest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-6059.96191, 15.9868021, -4904.7373, -0.444992423, -3.0874483e-09, 0.895534337, -3.64098796e-08, 1, -1.4644522e-08, -0.895534337, -3.91229982e-08, -0.444992423)
                CFrameBoss = CFrame.new(-5115.72754, 23.7664986, -5338.2207, 0.251453817, 1.48345061e-08, -0.967869282, 4.02796978e-08, 1, 2.57916977e-08, 0.967869282, -4.54708946e-08, 0.251453817)
            elseif _G.SelectBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" then
                MsBoss = "Cursed Captain [Lv. 1325] [Raid Boss]"
                NameBoss = "Cursed Captain"
                CFrameBoss = CFrame.new(916.928589, 181.092773, 33422, -0.999505103, 9.26310495e-09, 0.0314563364, 8.42916226e-09, 1, -2.6643713e-08, -0.0314563364, -2.63653774e-08, -0.999505103)
            elseif _G.SelectBoss == "Darkbeard [Lv. 1000] [Raid Boss]" then
                MsBoss = "Darkbeard [Lv. 1000] [Raid Boss]"
                NameBoss = "Darkbeard"
                CFrameBoss = CFrame.new(3876.00366, 24.6882591, -3820.21777, -0.976951957, 4.97356325e-08, 0.213458836, 4.57335361e-08, 1, -2.36868622e-08, -0.213458836, -1.33787044e-08, -0.976951957)
            elseif _G.SelectBoss == "Order [Lv. 1250] [Raid Boss]" then
                MsBoss = "Order [Lv. 1250] [Raid Boss]"
                NameBoss = "Order"
                CFrameBoss = CFrame.new(-6221.15039, 16.2351036, -5045.23584, -0.380726993, 7.41463495e-08, 0.924687505, 5.85604774e-08, 1, -5.60738549e-08, -0.924687505, 3.28013137e-08, -0.380726993)
            elseif _G.SelectBoss == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
                MsBoss = "Awakened Ice Admiral [Lv. 1400] [Boss]"
                NameBoss = "Awakened Ice Admiral"
                NameQuestBoss = "FrostQuest"
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(5669.33203, 28.2118053, -6481.55908, 0.921275556, -1.25320829e-08, 0.388910472, 4.72230788e-08, 1, -7.96414241e-08, -0.388910472, 9.17372489e-08, 0.921275556)
                CFrameBoss = CFrame.new(6407.33936, 340.223785, -6892.521, 0.49051559, -5.25310213e-08, -0.871432424, -2.76146022e-08, 1, -7.58250565e-08, 0.871432424, 6.12576301e-08, 0.49051559)
            elseif _G.SelectBoss == "Tide Keeper [Lv. 1475] [Boss]" then
                MsBoss = "Tide Keeper [Lv. 1475] [Boss]"
                 NameBoss = "Tide Keeper"
                NameQuestBoss = "ForgottenQuest"             
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-3053.89648, 236.881363, -10148.2324, -0.985987961, -3.58504737e-09, 0.16681771, -3.07832915e-09, 1, 3.29612559e-09, -0.16681771, 2.73641976e-09, -0.985987961)
                CFrameBoss = CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202)
            -- Thire World
            elseif _G.SelectBoss == "Stone [Lv. 1550] [Boss]" then
                MsBoss = "Stone [Lv. 1550] [Boss]"
                NameBoss = "Stone"
                NameQuestBoss = "PiratePortQuest"             
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-290, 44, 5577)
                CFrameBoss = CFrame.new(-1085, 40, 6779)
            elseif _G.SelectBoss == "Island Empress [Lv. 1675] [Boss]" then
                MsBoss = "Island Empress [Lv. 1675] [Boss]"
                 NameBoss = "Island Empress"
                NameQuestBoss = "AmazonQuest2"             
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(5443, 602, 752)
                CFrameBoss = CFrame.new(5659, 602, 244)
            elseif _G.SelectBoss == "Kilo Admiral [Lv. 1750] [Boss]" then
                MsBoss = "Kilo Admiral [Lv. 1750] [Boss]"
                NameBoss = "Kilo Admiral"
                NameQuestBoss = "MarineTreeIsland"             
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(2178, 29, -6737)
                CFrameBoss =CFrame.new(2846, 433, -7100)
            elseif _G.SelectBoss == "Captain Elephant [Lv. 1875] [Boss]" then
                MsBoss = "Captain Elephant [Lv. 1875] [Boss]"
                NameBoss = "Captain Elephant"
                NameQuestBoss = "DeepForestIsland"             
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-13232, 333, -7631)
                CFrameBoss = CFrame.new(-13221, 325, -8405)
            elseif _G.SelectBoss == "Beautiful Pirate [Lv. 1950] [Boss]" then
                MsBoss = "Beautiful Pirate [Lv. 1950] [Boss]"
                NameBoss = "Beautiful Pirate"
                NameQuestBoss = "DeepForestIsland2"             
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-12686, 391, -9902)
                CFrameBoss = CFrame.new(5182, 23, -20)
            elseif _G.SelectBoss == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
                MsBoss = "rip_indra True Form [Lv. 5000] [Raid Boss]"
                NameBoss = "rip_indra True Form"
                CFrameBoss = CFrame.new(-5359, 424, -2735)
            elseif _G.SelectBoss == "Longma [Lv. 2000] [Boss]" then
                MsBoss = "Longma [Lv. 2000] [Boss]"
                NameBoss = "Longma"
                CFrameBoss = CFrame.new(-10248.3936, 353.79129, -9306.34473)
            elseif _G.SelectBoss == "Soul Reaper [Lv. 2100] [Raid Boss]" then
                MsBoss = "Soul Reaper [Lv. 2100] [Raid Boss]"
                NameBoss = "Soul Reaper"
                CFrameBoss = CFrame.new(-9515.62109, 315.925537, 6691.12012)
            elseif _G.SelectBoss == "Cake Queen [Lv. 2175] [Boss]" then
                MsBoss = "Cake Queen [Lv. 2175] [Boss]"
                NameBoss = "Cake Queen"
                NameQuestBoss = "IceCreamIslandQuest"             
                LevelQuestBoss = 3
                CFrameQuestBoss = CFrame.new(-821.267456, 65.9448776, -10964.3994, 0.814093888, -3.67296735e-08, -0.58073324, 3.30765637e-08, 1, -1.6879099e-08, 0.58073324, -5.46748513e-09, 0.814093888)
                CFrameBoss = CFrame.new(-715.467102, 381.69104, -11019.8896, 0.955998719, -1.07319993e-08, -0.293370903, 5.00311881e-09, 1, -2.02781667e-08, 0.293370903, 1.7918131e-08, 0.955998719)
            end
        end
        Auto_Haki = true
        spawn(function()
            while wait(1) do
                if Auto_Haki then
                    if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
                    end
                end
            end
        end)
    
        spawn(function()
            while wait(.2) do
                if _G.AutoStats.Melee then
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Melee", 1)
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.2) do
                if _G.AutoStats.Defense then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 and Lv > 100 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Defense", 1)
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.2) do
                if _G.AutoStats.Sword then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 and Lv > 900 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Sword", 1)
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.2) do
                if _G.AutoStats.Gun then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 and Lv > 900 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Gun", 1)
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.1) do
                if _G.AutoStats.Fruit then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 and Lv > 900 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Demon Fruit", 1)
                    end
                end
            end
        end)
    
    
        if New_World or Three_World then
            spawn(function()
                while wait(.2) do
                    if AutoRaid then
                        for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
                            if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                pcall(function()
                                    repeat wait(.1)
                                        sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                                        v.Humanoid.Health = 0
                                        v.HumanoidRootPart.CanCollide = false
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        v.HumanoidRootPart.Transparency = 0.5
                                    until AutoRaid == false or not v.Parent or v.Humanoid.Health <= 0
                                end)
                            end
                        end
                    end
                end
            end)
            
            spawn(function()
                while wait(.2) do
                    if AutoRaid then
                        wait(2)
                        if POP then
                            Mix_Farm = true
                        end
                        if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") then
                            if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                                if New_World then
                                    fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
                                    repeat wait()
                                        wait(1)
                                    until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
                                elseif Three_World then
                                    fireclickdetector(game:GetService("Workspace").Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
                                    repeat wait()
                                        wait(1)
                                    until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
                                end
                            elseif game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
                                repeat wait()
                                    wait(1)
                                until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false
                                wait(1)
                                if _G.Hop and not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") then
                                    HopServer()
                                    wait(25)
                                end
                            end
                        elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") and game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                            wait(15)
                            if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                                if POP and not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") then
                                    if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                                        HopServer()
                                        wait(25)
                                    end
                                end
                            end
                        end
                    end
                end
            end)
            
            
            spawn(function()
                while wait(.2) do
                    if AutoRaid then
                        Fruit_Value = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                        if Fruit_Value == "Dark-Dark" then
                            _G.Setting_table.selectchip = "Dark"
                        elseif Fruit_Value == "Sand-Sand" then
                            _G.Setting_table.selectchip = "Sand"
                        elseif Fruit_Value == "Magma-Magma" then
                            _G.Setting_table.selectchip = "Magma"
                        elseif Fruit_Value == "Rumble-Rumble" then
                            _G.Setting_table.selectchip = "Rumble"
                        elseif Fruit_Value == "Flame-Flame" then
                            _G.Setting_table.selectchip = "Flame"
                        elseif Fruit_Value == "Ice-Ice" then
                            _G.Setting_table.selectchip = "Ice"
                        elseif Fruit_Value == "Light-Light" then
                            _G.Setting_table.selectchip = "Light"
                        elseif Fruit_Value == "Quake-Quake" then
                            _G.Setting_table.selectchip = "Quake"
                        elseif Fruit_Value == "Human-Human" then
                            _G.Setting_table.selectchip = "Human-Human: Buddha"
                        else
                            _G.Setting_table.selectchip = "Flame"
                        end
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", _G.Setting_table.selectchip)
                    end
                end
            end)
            spawn(function()
                while wait(.5) do
                    if AutoRaid then
                        if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                            TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame*CFrame.new(0,1,0))
                        end
                    end
                end
            end)
        
            spawn(function()
                while wait(.1) do
                    if AutoRaid then
                        pcall(function()
                            if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                                for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                    if v.Name == "Island 5" then
                                        TP2(v.CFrame*CFrame.new(0,70,0))
                                        --wait(10)
                                    end
                                end
                            elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                                for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                    if v.Name == "Island 4" then
                                        TP2(v.CFrame*CFrame.new(0,70,0))
                                        --wait(10)
                                    end
                                end
                            elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                                for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                    if v.Name == "Island 3" then
                                        TP2(v.CFrame*CFrame.new(0,70,0))
                                        --wait(10)
                                    end
                                end
                            elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                                for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                    if v.Name == "Island 2" then
                                        TP2(v.CFrame*CFrame.new(0,70,0))
                                        --wait(10)
                                    end
                                end
                            elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                                for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                    if v.Name == "Island 1" then
                                        TP2(v.CFrame*CFrame.new(0,70,0))
                                        --wait(10)
                                    end
                                end
                            end
                        end)
                    end
                end
            end)
        
        
            spawn(function()
                pcall(function()
                    while wait(1) do
                        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                        if AutoRaid and Lv >= 1800 then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Check")
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Awaken")
                        end
                    end
                end)
            end)
            
    
        end -- New World or Three World
    
        if Old_World then
    
            spawn(function()
                while wait(.2) do
                    if Auto_New_World and Old_World then
                        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                        local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                        if Lv >= 700 then
                            Auto_Farm = false
                            if Auto_Farm then
                                Auto_Farm = false
                            end
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective") == 1 then
                            else
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective")
                                wait(2)
                                EquipWeapon("Key")
                            end
                            repeat wait()
                                TP2(CFrame.new(1347.32947, 37.349369, -1325.44922, 0.538348913, 8.57539106e-08, 0.842722058, 8.61935634e-10, 1, -1.0230886e-07, -0.842722058, 5.58042359e-08, 0.538348913))
                            until (Vector3.new(1347.32947, 37.349369, -1325.44922)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                            wait(2)
                            for i,v in pairs(game.workspace.Enemies:GetChildren()) do
                                if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                    repeat wait()
                                        EquipWeapon(Melee_E)
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,15))
                                        game:GetService'VirtualUser':CaptureController()
                                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                    until v.Humanoid.Health <= 0 or not v.Parent or Auto_New_World == false
                                    wait(2)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                            end
                        end
                    end
                end
            end)
    
            spawn(function()
                while wait(.2) do
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if Old_World and Saber_Farm and Lv >= 200 and _G.Setting_table.Saber == nil then
                        Mix_Farm = true
                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") ~= 0 then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                            Auto_Farm = false
                            repeat wait()
                                TP(CFrame.new(-1609.29956, 40.0520697, 162.820404))
                            until (Vector3.new(-1609.29956, 40.0520697, 162.820404)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10
                            wait(3)
                            for i,v in pairs(game:GetService("Workspace").Map.Jungle.QuestPlates:GetChildren()) do
                                if v.Name == "Plate1" then
                                    repeat wait()
                                    TP2(v.Button.CFrame)
                                    until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                    wait(1)
                                end
                                if v.Name == "Plate2" then
                                    repeat wait()
                                    TP2(v.Button.CFrame)
                                    until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                    wait(1)
                                end
                                if v.Name == "Plate3" then
                                    repeat wait()
                                    TP2(v.Button.CFrame)
                                    until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                    wait(1)
                                end
                                if v.Name == "Plate4" then
                                    repeat wait()
                                    TP2(v.Button.CFrame)
                                    until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                    wait(1)
                                end
                                if v.Name == "Plate5" then
                                    repeat wait()
                                    TP2(v.Button.CFrame)
                                    until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                    wait(1)
                                end
                            end
                            wait(2)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1609.29956, 12.0520697, 162.820404, -0.993804812, 2.60902091e-08, 0.11113929, 3.47902116e-08, 1, 7.63408607e-08, -0.11113929, 7.97344768e-08, -0.993804812)
                            wait(2)
                            repeat wait()
                                EquipWeapon("Torch")
                                TP(CFrame.new(1113.9502, 4.92147732, 4350.91992, -0.60768199, 3.86533046e-08, 0.794180453, 6.00742425e-08, 1, -2.70375722e-09, -0.794180453, 4.60667628e-08, -0.60768199))
                            until (Vector3.new(1113.9502, 4.92147732, 4350.91992)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1
                            wait(1)
                            --fireclickdetector(game:GetService("Workspace").Map.Desert.Burn.Fire.ClickDetector)
                            wait(1)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1113.9502, 4.92147732, 4350.91992, -0.60768199, 3.86533046e-08, 0.794180453, 6.00742425e-08, 1, -2.70375722e-09, -0.794180453, 4.60667628e-08, -0.60768199)
                            wait(1)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1113.9502, 4.92147732, 4350.91992, -0.60768199, 3.86533046e-08, 0.794180453, 6.00742425e-08, 1, -2.70375722e-09, -0.794180453, 4.60667628e-08, -0.60768199)
                            wait(1)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1114.87708, 4.9214654, 4349.8501, -0.612586915, -9.68697833e-08, 0.790403247, -1.2634203e-07, 1, 2.4638446e-08, -0.790403247, -8.47679615e-08, -0.612586915)
                            wait(10)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1113.33618, 7.5484705, 4365.56396, -0.618000686, 2.54492516e-08, -0.786177576, -8.16741874e-09, 1, 3.87911392e-08, 0.786177576, 3.03939913e-08, -0.618000686)
                            wait(2)
                            repeat wait()
                                EquipWeapon("Cup")
                                TP(CFrame.new(1397.73975, 37.3480263, -1321.54456, -0.170597032, -4.99889588e-08, 0.985340893, 2.99880867e-08, 1, 5.59246409e-08, -0.985340893, 3.90890662e-08, -0.170597032))
                            until (Vector3.new(1397.73975, 37.3480263, -1321.54456)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2
                            wait(1)
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1397.73975, 37.3480263, -1321.54456, -0.170597032, -4.99889588e-08, 0.985340893, 2.99880867e-08, 1, 5.59246409e-08, -0.985340893, 3.90890662e-08, -0.170597032)
                            wait(3)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan")
                            wait(1)
                            Mob_Boss = true
                            Saber_Farm = false
                            
                        else
                            Auto_Farm = false
                            Mob_Boss = true
                            Saber_Farm = false
                        end
                    end
                end
            end)
            
            spawn(function()
                while wait(.2) do
                    if Mob_Boss then
                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 1 then
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Relic") or game.Players.LocalPlayer.Character:FindFirstChild("Relic") then
                                EquipWeapon("Relic")
                                repeat wait()
                                    EquipWeapon("Relic")
                                    TP2(CFrame.new(-1406.60925, 29.8520069, 4.5805192, 0.882920146, 3.62382622e-08, 0.469523162, -3.61928865e-09, 1, -7.03750587e-08, -0.469523162, 6.04362143e-08, 0.882920146))
                                until (Vector3.new(-1406.60925, 29.8520069, 4.5805192)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2
                                wait(1)
                                Saber_Kill = true
                                Mob_Boss = false
                            else
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
                            end
                        elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 0 then
                            if game.Workspace.Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
                                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                    if v.Name == "Mob Leader [Lv. 120] [Boss]" then
                                        repeat wait()
                                            EquipWeapon(Melee_E)
                                            v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                            TP(v.HumanoidRootPart.CFrame*CFrame.new(0,20,0))
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                        until not v.Parent or v.Humanoid.Health <= 0 or Mob_Boss == false
                                    end
                                end
                            elseif game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
                                TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]").HumanoidRootPart.CFrame)
                            end
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
                        end
                    end
                end
            end)
            
            spawn(function()
                while wait(.2) do
                    pcall(function()
                        if Saber_Kill then
                            if game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                    if v.Name == "Saber Expert [Lv. 200] [Boss]" then
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                        repeat wait()
                                            EquipWeapon(Melee_E)
                                            v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                            TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,15))
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                        until not v.Parent or v.Humanoid.Health <= 0 or Saber_Kill == false
                                        wait(2)
                                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Saber") or game.Players.LocalPlayer.Character:FindFirstChild("Saber") then
                                            _G.Setting_table.Saber = true
                                            savesetting()
                                        end
                                        wait(2)
                                        HopServer()
                                        wait(25)
                                    end
                                end
                            elseif game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") or game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                                TP(game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]").HumanoidRootPart.CFrame)
                            else
                                wait(5)
                                if not game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") and not game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                                    HopServer()
                                    wait(25)
                                end
                            end
                        end
                    end)
                end
            end)
    
        end -- Old World
    
        if New_World then
    
            spawn(function()
                while wait(.1) do
                    if Auto_Buy_Legendary_Sword then
                        local args = {
                            [1] = "LegendarySwordDealer",
                            [2] = "2"
                        }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                end
            end)
    
            spawn(function()
                while wait(.2) do
                    pcall(function()
                        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                        if Auto_Three_World and Lv >= 1500 and New_World then
                            World3 = true
                            if Auto_Farm then
                                Auto_Farm = false
                            end
                            Auto_Farm = false
                            Mix_Farm = true
                            AutoRaid = false
                            Inventory_Fruit = false
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 1 then
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                wait(15)
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 0 then
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check")
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Begin")
                                wait(5)
                                if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then
                                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                        if v.Name == "rip_indra [Lv. 1500] [Boss]" then
                                            repeat wait()
                                                if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 1 then
                                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                                    wait(20)
                                                end
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,20,0))
                                                EquipWeapon(Melee_E)
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                                game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                                            until v.Humanoid.Health <= 0 or not v.Parent
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check")
                                            game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
                                            wait(25)
                                        end
                                    end
                                end
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") ~= 0 then -- 
                                    game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Visible = true
                                    local Fruit_List = {
                                        "Quake-Quake",
                                        "Quake Fruit",
                                        "Human-Human: Buddha",
                                        "Human-Human: Buddha Fruit",
                                        "String-String",
                                        "String Fruit",
                                        "Rumble-Rumble",
                                        "Rumble Fruit",
                                        "Paw Fruit",
                                        "Paw-Paw",
                                        "Gravity Fruit",
                                        "Gravity-Gravity",
                                        "Dough Fruit",
                                        "Dough-Dough",
                                        "Shadow Fruit",
                                        "Shadow-Shadow",
                                        "Shadow Fruit",
                                        "Venom-Venom",
                                        "Venom Fruit",
                                        "Control Fruit",
                                        "Control-Control",
                                        "Dragon Fruit",
                                        "Dragon-Dragon"
                                    }
                                    wait(3)
                                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                                                    if v2:IsA("Tool") then
                                                        if v2.Name == Fruit_List[2] or v2.Name == Fruit_List[4] or v2.Name == Fruit_List[6] or v2.Name == Fruit_List[8] or v2.Name == Fruit_List[9] or v2.Name == Fruit_List[11] or v2.Name == Fruit_List[13] or v2.Name == Fruit_List[15] or v2.Name == Fruit_List[19] or v2.Name == Fruit_List[20] or v2.Name == Fruit_List[22] then
                                                            Auto_Farm = false
                                                            EquipWeapon(v2.Name)
                                                            wait(1)
                                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
                                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
                                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
                                                            wait(2)
                                                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
                                                                game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
                                                                wait(25)
                                                            end
                                                        end
                                                    end
                                                end
                                        for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Container.Stored.ScrollingFrame.Frame:GetChildren()) do
                                            if v.Name == Fruit_List[1] or v.Name == Fruit_List[3] or v.Name == Fruit_List[5] or v.Name == Fruit_List[7] or v.Name == Fruit_List[10] or v.Name == Fruit_List[12] or v.Name == Fruit_List[14] or v.Name == Fruit_List[16] or v.Name == Fruit_List[18] or v.Name == Fruit_List[21] or v.Name == Fruit_List[23] then
                                                Inventory_Fruit = false
                                                Open_Don_Swan = false
                                                wait(1)
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v.Name)
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                                                    if v2:IsA("Tool") then
                                                        if v2.Name == Fruit_List[2] or v2.Name == Fruit_List[4] or v2.Name == Fruit_List[6] or v2.Name == Fruit_List[8] or v2.Name == Fruit_List[9] or v2.Name == Fruit_List[11] or v2.Name == Fruit_List[13] or v2.Name == Fruit_List[15] or v2.Name == Fruit_List[19] or v2.Name == Fruit_List[20] or v2.Name == Fruit_List[22] then
                                                            Auto_Farm = false
                                                            EquipWeapon(v2.Name)
                                                            wait(1)
                                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
                                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
                                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
                                                            wait(2)
                                                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
                                                                game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
                                                                wait(25)
                                                            end
                                                        end
                                                    end
                                                end
                                            else
                                                HopServer()
                                                wait(25)
                                            end
                                        end
                            else
                                if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Don Swan [Lv. 1000] [Boss]" then
                                                repeat wait()
                                                    spawn(function()
                                                        wait(10)
                                                        if v.Humanoid.Health == v.Humanoid.MaxHealth then
                                                            HopServer()
                                                            wait(25)
                                                        end
                                                    end)
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    EquipWeapon(Melee_E)
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                                    game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                                                until v.Humanoid.Health <= 0 or not v.Parent
                                                wait(1)
                                                game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
                                                wait(20)
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame)
                                        wait(2)
                                    end
                                else
                                    wait(5)
                                    if not game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
                                        HopServer()
                                        wait(25)
                                    end
                                end
                            end
                        end
                    end)
                end
            end)
    
            spawn(function()
                while wait(.2) do
                    if Bartlio_Farm and New_World and Mix_Farm == nil then
                        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                        if Lv >= 900 and _G.Setting_table.Bartlio == nil then
                            Auto_Farm = false
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
                                if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                                    if game.workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
                                        for i,v in pairs(game.workspace.Enemies:GetChildren()) do
                                            if v.Name == "Swan Pirate [Lv. 775]" then
                                                _G.PosMon = v.HumanoidRootPart.CFrame
                                                StatrMagnet = true
                                                repeat wait()
                                                    EquipWeapon(Melee_E)
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                                until v.Humanoid.Health <= 0 or not v.Parent or Bartlio_Farm ==false
                                                StatrMagnet = false
                                            end
                                        end
                                    elseif game:GetService("ReplicatedStorage"):FindFirstChild("Swan Pirate [Lv. 775]") then
                                        TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Swan Pirate [Lv. 775]").HumanoidRootPart.CFrame*CFrame.new(0,20,0))
                                    end
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","BartiloQuest",1)
                                end
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
                                _G.SelectBoss = "Jeremy [Lv. 850] [Boss]"
                                CheckQuestBoss()
                                if game.workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
                                    for i,v in pairs(game.workspace.Enemies:GetChildren()) do
                                        if v.Name == "Jeremy [Lv. 850] [Boss]" then
                                            repeat wait()
                                                EquipWeapon(Melee_E)
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                            until v.Humanoid.Health <= 0 or not v.Parent or Bartlio_Farm == false
                                        end
                                    end
                                else
                                    TP(CFrameBoss)
                                end
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
                                repeat wait()
                                    TP2(CFrame.new(-1836, 11, 1714))
                                until (Vector3.new(-1836, 11, 1714)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1836, 11, 1714)
                                    wait(1)
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1850.49329, 13.1789551, 1750.89685)
                                    wait(1)
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.87305, 19.3777466, 1712.01807)
                                    wait(1)
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1803.94324, 16.5789185, 1750.89685)
                                    wait(1)
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.55835, 16.8604317, 1724.79541)
                                    wait(1)
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1869.54224, 15.987854, 1681.00659)
                                    wait(1)
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1800.0979, 16.4978027, 1684.52368)
                                    wait(1)
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1819.26343, 14.795166, 1717.90625)
                                    wait(1)
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1813.51843, 14.8604736, 1724.79541)
                            else
                                _G.Setting_table.Bartlio = true
                                savesetting()
                                game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
                                wait(20)
                            end
                        end
                    end
                end
            end)
    
            spawn(function()
                while wait(2) do
                    if Kabucha_Farm and _G.Setting_table.Kabucha == nil and New_World then
                        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                        if FG >= 1500 and Lv > 1000 and not game.Players.LocalPlayer.Backpack:FindFirstChild("Kabucha") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","1")
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","2")
                        end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Kabucha") or game.Players.LocalPlayer.Character:FindFirstChild("Kabucha") then
                            _G.Setting_table.Kabucha = true
                            savesetting()
                        end
                    end
                end
            end)
    
            spawn(function()
                while wait(.2) do
                    pcall(function()
                        if Acidum_Rifle_Farm and _G.Setting_table.Acidum_Rifle == nil and New_World and Mix_Farm == nil or Acidum_Rifle_Farm_Ex then
                            if game.Players.LocalPlayer.Character:FindFirstChild("Acidum Rifle") or game.Players.LocalPlayer.Backpack:FindFirstChild("Acidum Rifle") then
                                _G.Setting_table.Acidum_Rifle = true
                                savesetting()
                            else
                                if game.Workspace.Enemies:FindFirstChild("Core") or game.ReplicatedStorage:FindFirstChild("Core") then
                                    Acidum_Rifle_Farm_Ex = true
                                    Mix_Farm = true
                                    if game.Workspace.Enemies:FindFirstChild("Core") then
                                        for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                            if v.Name == "Core" then
                                                repeat wait()
                                                    EquipWeapon(Melee_E)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                                until v.Humanoid.Health <= 0 or not v.Parent or Acidum_Rifle_Farm == false
                                                wati(1)
                                                game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
                                                wait(25)
                                            end
                                        end
                                    else
                                        TP(CFrame.new(402.404296875, 182.53373718262, -414.73394775391))
                                    end
                                end
                            end
                        end
                    end)
                end
            end)
        end
    
        if _G.Hop_Superhuman_Ex then
            local args = {
                [1] = "BuyBlackLeg"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end
    if Superhuman_A and _G.Setting_table.Superhuman_H == nil then
        spawn(function()
            while wait(.1) do
                if Superhuman_A and not _G.Hop_Superhuman_Ex then
                        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                        local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if game:GetService("Players").LocalPlayer.Data.Beli.Value > 150000 then
                                if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
                                    local args = {
                                        [1] = "BuyBlackLeg"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                end   
                            end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") and game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman").Level.Value < 330 then
                            _G.Select_Weapon = "Superhuman"
                            if IKAI == nil then
                                _G.Setting_table.Superhuman_H = true
                                savesetting()
                            end
                            if _G.Hop_Superhuman then
                                Auto_Farm_Melee = true
                            end
                        elseif _G.Hop_Superhuman and game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") and game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman").Level.Value >= 330 then
                            _G.Hop_Superhuman_Ex = true
                        end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                            _G.Select_Weapon = "Black Leg"
                            if _G.Hop_Superhuman then
                                Auto_Farm_Melee = true
                            end
                        end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                            _G.Select_Weapon = "Electro"
                            if _G.Hop_Superhuman then
                                Auto_Farm_Melee = true
                            end
                        end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                            _G.Select_Weapon = "Fishman Karate"
                            if _G.Hop_Superhuman then
                                Auto_Farm_Melee = true
                            end
                        end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                            _G.Select_Weapon = "Dragon Claw"
                            if _G.Hop_Superhuman then
                                Auto_Farm_Melee = true
                            end
                        end
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local args = {
                                    [1] = "BuyElectro"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            end
                            if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local args = {
                                    [1] = "BuyElectro"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            end
                            
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local args = {
                                    [1] = "BuyFishmanKarate"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            end
                            if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local args = {
                                    [1] = "BuyFishmanKarate"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            end
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                                if FG >= 1500 then
                                    local args = {
                                        [1] = "BlackbeardReward",
                                        [2] = "DragonClaw",
                                        [3] = "2"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                elseif _G.Hop_Superhuman then
                                    _G.Hop_Superhuman_Ex = true
                                end
                            end
                            if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                                if FG >= 1500 then
                                    local args = {
                                        [1] = "BlackbeardReward",
                                        [2] = "DragonClaw",
                                        [3] = "2"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                elseif _G.Hop_Superhuman then
                                    _G.Hop_Superhuman_Ex = true
                                end
                            end
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                                if Beli >= 300000 then
                                    local args = {
                                        [1] = "BuySuperhuman"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                else
                                    _G.Select_Weapon = "Dragon Claw"
                                end
                            end
                            if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                                if Beli >= 300000 then
                                    local args = {
                                        [1] = "BuySuperhuman"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                else
                                    _G.Select_Weapon = "Dragon Claw"
                                end
                            end
                end
            end
        end)
    elseif Death_Step_A and _G.Setting_table.Death_Step_H == nil then
        spawn(function()
            while wait(.1) do
                if Death_Step_A and not _G.Hop_Death_Step_Ex then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step").Level.Value < 330 then
                        _G.Select_Weapon = "Death Step"
                        if IKAI == nil then
                            _G.Setting_table.Death_Step_H = true
                            savesetting()
                        end
                        if _G.Hop_Death_Step then
                            Auto_Farm_Melee = true
                        end
                        if PIO then
                            Mix_Farm = nil
                            PIO = nil
                        end
                    elseif _G.Hop_Death_Step and game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step").Level.Value >= 330 then
                        _G.Hop_Death_Step_Ex = true
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                        _G.Select_Weapon = "Black Leg"
                        if _G.Hop_Death_Step then
                            Auto_Farm_Melee = true
                        end
                    elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and not game.Players.LocalPlayer.Character:FindFirstChild("Death Step") then
                        local args = {
                            [1] = "BuyBlackLeg"
                        }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 400 then
                        local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                        if FG >= 5000 and Beli >= 3000000 then
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") ~= 1 then
                                if New_World then
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
                                    Mix_Farm = true
                                    PIO = true
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
                                                until v.Humanoid.Health <= 0 or not v.Parent
                                                
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame)
                                    end
                                end
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 1 then
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
                            elseif _G.Hop_Death_Step then
                                _G.Hop_Death_Step_Ex = true
                            end
                        elseif _G.Hop_Death_Step then
                            _G.Hop_Death_Step_Ex = true
                        end
                    end
                    if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 then
                        local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                        if FG >= 5000 and Beli >= 3000000 then
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") ~= 1 then
                                if New_World then
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
                                    Mix_Farm = true
                                    PIO = true
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
                                                until v.Humanoid.Health <= 0 or not v.Parent
                                                
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame)
                                    end
                                end
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 1 then
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
                            elseif _G.Hop_Death_Step then
                                _G.Hop_Death_Step_Ex = true
                            end
                        elseif _G.Hop_Death_Step then
                            _G.Hop_Death_Step_Ex = true
                        end
                    end
                end
            end
        end)
    elseif _G.Setting_table.Sharkman_Karate_H == nil and Sharkman_Karate_A then
        spawn(function()
            while wait(.1) do
                if Sharkman_Karate_A and not _G.Hop_Sharkman_Karate_Ex then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate").Level.Value < 330 then
                        _G.Select_Weapon = "Sharkman Karate"
                        if IKAI == nil then
                            _G.Setting_table.Sharkman_Karate_H = true
                            savesetting()
                        end
                        if _G.Hop_Sharkman_Karate then
                            Auto_Farm_Melee = true
                        end
                    elseif _G.Hop_Sharkman_Karate and game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate").Level.Value >= 330 then
                        _G.Hop_Sharkman_Karate_Ex = true
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                        _G.Select_Weapon = "Fishman Karate"
                        if _G.Hop_Sharkman_Karate then
                            Auto_Farm_Melee = true
                        end
                    elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Sharkman Karate") then
                        local args = {
                                [1] = "BuyFishmanKarate"
                            }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 then
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 0 then
                                if New_World then
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
                                    Mix_Farm = true
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Tide Keeper [Lv. 1475] [Boss]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
                                                until v.Humanoid.Health <= 0 or not v.Parent
                                                wait(2)
                                                if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then  
                                                    if game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key") then
                                                        EquipWeapon("Water Key")
                                                        wait(0.5)
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
                                                    end
                                                end
                                                Mix_Farm = nil
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame)
                                    end
                                elseif _G.Hop_Sharkman_Karate then
                                    _G.Hop_Sharkman_Karate_Ex = true
                                end
                            elseif FG >= 5000 and Beli >= 3000000 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 1 then
                                local args = {
                                    [1] = "BuySharkmanKarate",
                                    [2] = true
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                local args = {
                                    [1] = "BuySharkmanKarate"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            elseif _G.Hop_Sharkman_Karate then
                                _G.Hop_Sharkman_Karate_Ex = true
                            end
                        end
                        if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 400 then
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 0 then
                                if New_World then
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
                                    Mix_Farm = true
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Tide Keeper [Lv. 1475] [Boss]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
                                                until v.Humanoid.Health <= 0 or not v.Parent
                                                wait(2)
                                                if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then  
                                                    if game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key") then
                                                        EquipWeapon("Water Key")
                                                        wait(0.5)
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
                                                    end
                                                end
                                                Mix_Farm = nil
                                              
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame)
                                    end
                                elseif _G.Hop_Sharkman_Karate then
                                    _G.Hop_Sharkman_Karate_Ex = true
                                end
                            elseif FG >= 5000 and Beli >= 3000000 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 1 then
                                local args = {
                                    [1] = "BuySharkmanKarate",
                                    [2] = true
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                local args = {
                                    [1] = "BuySharkmanKarate"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            elseif _G.Hop_Sharkman_Karate then
                                _G.Hop_Sharkman_Karate_Ex = true
                            end
                        end
                    
                end
            end
        end)
    elseif _G.Setting_table.Electric_Claw_H == nil and Electric_Claw_A then
        spawn(function()
            while wait(.1) do
                if Electric_Claw_A and not _G.Hop_Electric_Claw_Ex then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw").Level.Value < 330 then
                        _G.Select_Weapon = "Electric Claw"
                        if IKAI == nil then
                            _G.Setting_table.Electric_Claw_H = true
                            savesetting()
                        end
                        if _G.Hop_Electric_Claw then
                            Auto_Farm_Melee = true
                        end
                        if PIO then
                            Mix_Farm = nil
                            PIO = nil
                        end
                    elseif _G.Hop_Electric_Claw and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw").Level.Value > 330 then
                        _G.Hop_Electric_Claw_Ex = true
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                        _G.Select_Weapon = "Electro"
                        if _G.Hop_Electric_Claw then
                            Auto_Farm_Melee = true
                        end
                    elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and not game.Players.LocalPlayer.Character:FindFirstChild("Electro") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw") then
                        local args = {
                                [1] = "BuyElectro"
                            }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 and Three_World then
                            local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                            local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if FG >= 5000 and Beli >= 3000000 then
                                if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true) == 4 then
                                    if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start") == nil then
                                        if Three_World then
                                        else
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                            wait(25)
                                        end
                                        Mix_Farm = true
                                        PIO = true
                                        TP2(CFrame.new(-12548, 337, -7481))
                                    end
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
                                end
                            elseif _G.Hop_Electric_Claw then
                                _G.Hop_Electric_Claw_Ex = true
                            end
                        end
                        if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 and Three_World then
                            local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                            local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if FG >= 5000 and Beli >= 3000000 then
                                if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true) == 4 then
                                    if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start") == nil then
                                        if Three_World then
                                        else
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                            wait(25)
                                        end
                                        Mix_Farm = true
                                        PIO = true
                                        TP2(CFrame.new(-12548, 337, -7481))
                                    end
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
                                end
                            elseif _G.Hop_Electric_Claw then
                                _G.Hop_Electric_Claw_Ex = true
                            end
                        end
                    
                end
            end
        end)
    elseif _G.Setting_table.Dragon_Talon_H == nil and Dragon_Talon_A then
        spawn(function()
            while wait(.1) do
                if Dragon_Talon_A and not _G.Hop_Dragon_Talon_Ex then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon").Level.Value < 330 then
                        _G.Select_Weapon = "Dragon Talon"
                        if IKAI == nil then
                            _G.Setting_table.Dragon_Talon_H = true
                            savesetting()
                        end
                        if _G.Hop_Dragon_Talon then
                            Auto_Farm_Melee = true
                        end
                        Fire_Shop = false
                    elseif _G.Hop_Dragon_Talon and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon").Level.Value >= 330 then
                        _G.Hop_Dragon_Talon_Ex = true
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                        _G.Select_Weapon = "Dragon Claw"
                        if Three_World then
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                            wait(25)
                        end
                        if _G.Hop_Dragon_Talon then
                            Auto_Farm_Melee = true
                        end
                    elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Talon") then
                        local args = {
                                [1] = "BlackbeardReward",
                                [2] = "DragonClaw",
                                [3] = "2"
                            }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 400 then
                            local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                            local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if FG >= 5000 and Beli >= 3000000 then
                                Fire_Shop = true
                                if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Bones", "Buy",1,1)
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
                                elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
                                else
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
                                end
                            elseif _G.Hop_Dragon_Talon then
                                _G.Hop_Dragon_Talon_Ex = true
                            end
                        elseif _G.Hop_Dragon_Talon then
                            _G.Hop_Dragon_Talon_Ex = true
                        end
                        if FG >= 5000 and Beli >= 3000000 and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 400 then
                            local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                            local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if FG >= 5000 and Beli >= 3000000 then
                                Fire_Shop = true
                                if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Bones", "Buy",1,1)
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
                                elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
                                else
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
                                end
                            elseif _G.Hop_Dragon_Talon then
                                _G.Hop_Dragon_Talon_Ex = true
                            end
                        elseif _G.Hop_Dragon_Talon then
                            _G.Hop_Dragon_Talon_Ex = true
                        end
                    
                end
            end
        end)
    end
        
        spawn(function()
            while wait(.2) do
                if Fire_Shop then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Fire Essence") or game.Players.LocalPlayer.Character:FindFirstChild("Fire Essence") then
                        local args = {
                            [1] = "BuyDragonTalon",
                            [2] = true
                        }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                        Fire_Shop = false
                    else
                        local args = {
                            [1] = "Bones",
                            [2] = "Check"
                        }
                        
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                        -- Script generated by SimpleSpy - credits to exx#9394
                        
                        local args = {
                            [1] = "Bones",
                            [2] = "Buy",
                            [3] = 1,
                            [4] = 1
                        }
                        
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                end
            end
        end)
    
        if Three_World then
    
            spawn(function()
                while wait(.5) do
                    if Three_World and BuddySword_A then
                        if Mix_Farm == nil or BuddySword_Farm then
                            if game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
                                Mix_Farm = true
                                BuddySword_Farm = true
                                if game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
                                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                        if v.Name == "Cake Queen [Lv. 2175] [Boss]" then
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                EquipWeapon(_G.Select_Weapon)
                                                TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
                                            until v.Humanoid.Health <= 0 or not v.Parent or BuddySword_A == false
                                            Mix_Farm = nil
                                            BuddySword_Farm = nil
                                        end
                                    end
                                else
                                    TP(game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]").HumanoidRootPart.CFrame)
                                end
                            elseif _G.Hop_BuddySword then
                                wait(5)
                                if not game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
                                    _G.Hop_BuddySword_Ex = true
                                end
                            end
                        end
                    end
                end
            end)
    
            spawn(function()
                while wait(.1) do
                    pcall(function()
                        if DarkDagger_A then
                            if Three_World then
                            else
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                wait(25)
                            end
                            if Mix_Farm == nil or DarkDagger_Farm then
                                if game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                                    
                                    Mix_Farm = true
                                    DarkDagger_Farm = true
                                    if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                                        for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                            if v.Name == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                repeat wait()
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                until v.Humanoid.Health <= 0 or not v.Parent or DarkDagger_A == false
                                                
                                                Mix_Farm = nil
                                                DarkDagger_Farm = nil
                                            end
                                        end
                                    else
                                        TP2(game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
                                    end
                                end
                            end
                        end
                    end)
                end
            end)
            
            spawn(function()
                while wait(.1) do
                    pcall(function()
                        if Hallow_Scryte_A then
                            if Three_World then
                            else
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                wait(25)
                            end
                            if Mix_Farm == nil or Hallow_Scryte_Farm then
                                if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
                                    
                                    Mix_Farm = true
                                    Hallow_Scryte_Farm = true
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Soul Reaper [Lv. 2100] [Raid Boss]" then
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                repeat wait()
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
                                                until v.Humanoid.Health <= 0 or not v.Parent or Hallow_Scryte_A == nil
                                                
                                                Mix_Farm = nil
                                                Hallow_Scryte_Farm = nil
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]").HumanoidRootPart.CFrame)
                                    end
                                elseif _G.Hop_HallowScryte then
                                    wait(5)
                                    if not game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
                                        _G.Hop_HallowScryte_Ex = true
                                    end
                                end
                            end
                        end
                    end)
                end
            end)
            
            spawn(function()
                while wait(.5) do
                    if Spikey_Trident_A then
                        if Mix_Farm == nil or Spikey_Trident_Farm then
                            if game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
                                
                                Mix_Farm = true
                                Spikey_Trident_Farm = true
                                if game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
                                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                        if v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" then
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                v.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                                EquipWeapon(_G.Select_Weapon)
                                                TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
                                            until v.Humanoid.Health <= 0 or not v.Parent or Spikey_Trident_A == false
                                            
                                            Mix_Farm = nil
                                            Spikey_Trident_Farm = true
                                        end
                                    end
                                else
                                    TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
                                end
                            elseif _G.Hop_SpikeyTrident then
                                wait(5)
                                if not game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") and not game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
                                    _G.Hop_SpikeyTrident_Ex = true
                                end
                            end
                        end   
                    end
                end
            end)
            
            spawn(function()
                while wait(.5) do
                    pcall(function()
                        if Yama_A then
                            if Mix_Farm == nil or Yama_Farm then
                                if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress") < 30 then
                                    if game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
                                        
                                        Mix_Farm = true
                                        Yama_Farm = true
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                                        if game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
                                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                                if v.Name == "Urban [Lv. 1750]" then
                                                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                        if tostring(v2.ToolTip) == "Melee" then
                                                            Melee_E = v2.Name
                                                        end
                                                    end
                                                    if _G.Select_Weapon == nil then
                                                        _G.Select_Weapon = Melee_E
                                                    end
                                                    repeat wait()
                                                        EquipWeapon(_G.Select_Weapon)
                                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                        TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                        game:GetService'VirtualUser':CaptureController()
                                                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                    until v.Humanoid.Health <= 0 or not v.Parent or Yama_A == false
                                                    K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                    
                                                    Mix_Farm = nil
                                                    Yama_Farm = nil
                                                end
                                            end
                                        else
                                            TP(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame)
                                        end
                                    elseif game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
                                        
                                        Mix_Farm = true
                                        Yama_Farm = true
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                                        if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
                                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                                if v.Name == "Diablo [Lv. 1750]" then
                                                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                        if tostring(v2.ToolTip) == "Melee" then
                                                            Melee_E = v2.Name
                                                        end
                                                    end
                                                    if _G.Select_Weapon == nil then
                                                        _G.Select_Weapon = Melee_E
                                                    end
                                                    repeat wait()
                                                        EquipWeapon(_G.Select_Weapon)
                                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                        TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                        game:GetService'VirtualUser':CaptureController()
                                                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                    until v.Humanoid.Health <= 0 or not v.Parent or Yama_A == false
                                                    K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                    
                                                    Mix_Farm = nil
                                                    Yama_Farm = nil
                                                end
                                            end
                                        else
                                            TP(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame)
                                        end
                                    elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                        
                                        Mix_Farm = true
                                        Yama_Farm = true
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                                        if game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                                if v.Name == "Deandre [Lv. 1750]" then
                                                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                        if tostring(v2.ToolTip) == "Melee" then
                                                            Melee_E = v2.Name
                                                        end
                                                    end
                                                    if _G.Select_Weapon == nil then
                                                        _G.Select_Weapon = Melee_E
                                                    end
                                                    repeat wait()
                                                        EquipWeapon(_G.Select_Weapon)
                                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                        TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                        game:GetService'VirtualUser':CaptureController()
                                                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                    until v.Humanoid.Health <= 0 or not v.Parent or Yama_A == false
                                                    K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                    
                                                    Mix_Farm = nil
                                                    Yama_Farm = nil
                                                end
                                            end
                                        else
                                            TP(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame)
                                        end
                                    elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Urban (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Deandre (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Diablo (0/1)" then
                                        HopServer()
                                    elseif _G.Hop_Yama then
                                        wait(5)
                                        if not game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                            _G.Hop_Yama_Ex = true
                                        end
                                    end
                                elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress") >= 30 then
                                    
                                    Mix_Farm = true
                                    Yama_Farm = true
                                    if (game.Workspace.Map.Waterfall.SealedKatana.Handle.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 300 then
                                        TP(game.Workspace.Map.Waterfall.SealedKatana.Handle.CFrame)
                                    end
                                    if game.Workspace.Enemies:FindFirstChild("Ghost [Lv. 1500]") then
                                        for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                            if v.Name == "Ghost [Lv. 1500]" then
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                until v.Humanoid.Health <= 0 or not v.Parent or Yama_A == false
                                                K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                
                                                Mix_Farm = nil
                                                Yama_Farm = nil
                                            end
                                        end
                                    elseif not game.Workspace.Enemies:FindFirstChild("Ghost [Lv. 1500]") then
                                        fireclickdetector(game.Workspace.Map.Waterfall.SealedKatana.Handle.ClickDetector)
                                    end
                                end
                            end
                        end
                    end)
                end
            end)
    
            spawn(function()
                while wait(.5) do
                    if Canvander_A then
                        if Mix_Farm == nil or Canvander_Farm then
                            if game:GetService("ReplicatedStorage"):FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
                                Mix_Farm = true
                                Canvander_Farm = true
                                if game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
                                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                        if v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" then
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                v.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                                EquipWeapon(_G.Select_Weapon)
                                                TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
                                            until v.Humanoid.Health <= 0 or not v.Parent or Canvander_A == false
                                            
                                            Mix_Farm = nil
                                            Canvander_Farm = true
                                        end
                                    end
                                else
                                    TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
                                end
                            elseif _G.Hop_Canvander then
                                wait(5)
                                if not game:GetService("ReplicatedStorage"):FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") and not game:GetService("Workspace").Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
                                    _G.Hop_Canvander_Ex = true
                                end
                            end
                        end   
                    end
                end
            end)
    
        end
    
        spawn(function()
            while wait(.1) do
                if Auto_Farm and Mix_Farm == nil then
                    pcall(function()
                        if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                            StatrMagnet = false
                            FastAttack = false
                            CheckLevel()
                            if Redeem and Yoos == nil then
                                function UseCode(Text)
                                    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
                                end
                                local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                                if _G.Redeem_Lv == nil then
                                    _G.Redeem_Lv = 300
                                end
                                if Lv >= _G.Redeem_Lv and Yoos == nil then
                                    UseCode("Sub2Fer999")
                                    UseCode("Enyu_is_Pro")
                                    UseCode("Magicbus")
                                    UseCode("JCWK")
                                    UseCode("Starcodeheo")
                                    UseCode("Bluxxy")
                                    UseCode("THEGREATACE")
                                    UseCode("SUB2GAMERROBOT_EXP1")
                                    UseCode("StrawHatMaine")
                                    UseCode("Sub2OfficialNoobie")
                                    UseCode("SUB2NOOBMASTER123")
                                    UseCode("Sub2Daigrock")
                                    UseCode("Axiore")
                                    UseCode("TantaiGaming")
                                    UseCode("STRAWHATMAINE")
                                    Yoos = true
                                end
                            end
                            if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 500 then
                                TP(CFrameQ)
                            else
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                            end
                        elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                            CheckLevel()
                            StatrMagnet = false
                            if game.Workspace.Enemies:FindFirstChild(Ms) then
                                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                    if v.Humanoid.Health > 0 and v.Name == Ms and (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                                        if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
                                            StatrMagnet = true
                                            if v.Humanoid:FindFirstChild("Animator") then
                                                v.Humanoid.Animator:Destroy()
                                            end
                                            P = v
                                            v.HumanoidRootPart.CanCollide = false
                                            _G.PosMon = v.HumanoidRootPart.CFrame
                                            v.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                            sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            FastAttack = true
                                            repeat wait(.2)
                                                EquipWeapon(_G.Select_Weapon)
                                                TP(P.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                            until P.Humanoid.Health <= 0 or not P.Parent or Auto_Farm == false or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false or Mix_Farm 
                                            StatrMagnet = false
                                            FastAttack = true
                                        else
                                            StatrMagnet = false
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                                        end
                                    end
                                end
                            elseif not game.Workspace.Enemies:FindFirstChild(Ms) and not game:GetService("ReplicatedStorage"):FindFirstChild(Ms) then
                                if (CFrameMon.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 5 then
                                    TP(CFrameMon)
                                    FastAttack = false
                                end
                            end
                        end
                    end)
                end
            end
        end)
    
        spawn(function()
            while wait(.2) do
                pcall(function()
                    if not Mix_Farm then
                        if Auto_Farm_Melee then
                            CheckLevel()
                            if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                                StatrMagnet = false
                                CheckLevel()
                                if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 500 then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                else
                                    repeat wait(.3)
                                        TP2(CFrameQ)
                                    until (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 400
                                end
                            else
                                if (CFrameMon.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
                                    StatrMagnet = false
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v.Humanoid.Health > 0 and v:FindFirstChild("Humanoid") or v.Humanoid.Health > 0 and v:FindFirstChild("HumanoidRootPart") then
                                            if (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 2000 then
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 100 then
                                                    _G.Mon = v
                                                elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 500 then
                                                    _G.Mon = v
                                                elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1000 then
                                                    _G.Mon = v
                                                elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                                                    _G.Mon = v
                                                elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
                                                    _G.Mon = v
                                                end
                                                _G.PosMon = _G.Mon.HumanoidRootPart.CFrame
                                                CFrameMon = _G.Mon.HumanoidRootPart.CFrame
                                                _G.Mon.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                                StatrMagnet = true
                                                repeat wait()
                                                    EquipWeapon(Melee_E)
                                                    TP(_G.Mon.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                                until _G.Mon.Humanoid.Health <= 0 or not _G.Mon.Parent or Auto_Farm_Melee == false
                                                StatrMagnet = false
                                            end
                                        else
                                            TP2(CFrameMon)
                                        end
                                    end
                                else
                                    TP2(CFrameMon*CFrame.new(0,35,0))
                                end
                            end
                        end
                    end
                end)
            end
        end)
    
        
    else
    
        if  _G.ColorP == nil then
            _G.ColorP = "Default" -- "RGB","Default"
        end
    
        if not game:IsLoaded() then 
            repeat game.Loaded:Wait() 
        until game:IsLoaded() end
            
        
        Old_World = false
        New_World = false
        Three_World = false
        local placeId = game.PlaceId
        if placeId == 2753915549 then
            Old_World = true
        elseif placeId == 4442272183 then
            New_World = true
        elseif placeId == 7449423635 then
            Three_World = true
        end
        _G.Color = Color3.fromRGB(255,255,255)
        repeat wait()
            if game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Visible == true then
                if _G.Teams == "Pirates" then
                    for i,v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.MouseButton1Click)) do
                        v.Function()
                    end
                elseif _G.Teams == "Marines" then
                    for i,v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.MouseButton1Click)) do
                        v.Function()
                    end
                else
                    for i,v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.MouseButton1Click)) do
                        v.Function()
                    end
                end
                if game.Players.localPlayer.Neutral == false then
                    IKAI = true
                end
            end
        until game.Players.localPlayer.Neutral == false
        _G.Setting_table = {
            FastAttack = true,
            Spawn_Set = true
        }
        
        Name_Me = tostring(game.Players.LocalPlayer)
        local filename = tostring(Name_Me)..".txt"
        
        function savesetting()
            local json
            local HttpService = game:GetService("HttpService")
            if (writefile) then
                json = HttpService:JSONEncode(_G.Setting_table)
                writefile(filename, json)
            else
                print("-- Sorry You Noob --")
            end
        end
        
        function loadsetting()
            local HttpService = game:GetService("HttpService")
            if (readfile and isfile and isfile(filename)) then
                _G.Setting_table = HttpService:JSONDecode(readfile(filename))
                -- print("-- New Value --")
                for i,v in pairs(_G.Setting_table) do
                    -- print(i,v)
                end
            end
        end
        loadsetting()
        
        spawn(function()
            while wait(2) do
                if _G.Hop then
                    if _G.Hop_Saber and _G.Hop_Saber_Ex == nil then
                        Saber_Farm = true
                    elseif _G.Hop_PoleV1 and _G.Hop_PoleV1_Ex == nil then
                        Pole_V1_Hop = true
                    elseif _G.Hop_Superhuman and _G.Hop_Superhuman_Ex == nil then
                        Superhuman_A = true
                    elseif _G.Hop_Sharkman_Karate and _G.Hop_Sharkman_Karate_Ex == nil then
                        Sharkman_Karate_A = true
                    elseif _G.Hop_Death_Step and _G.Hop_Death_Step_Ex == nil then
                        Death_Step_A = true
                    elseif _G.Hop_Electric_Claw and _G.Hop_Electric_Claw_Ex == nil then
                        Electric_Claw_A = true
                    elseif _G.Hop_Dragon_Talon and _G.Hop_Dragon_Talon_Ex == nil then
                        Dragon_Talon_A = true
                    elseif _G.Hop_BuddySword and _G.Hop_BuddySword_Ex == nil then
                        BuddySword_A = true
                    elseif _G.Hop_DarkDagger and _G.Hop_DarkDagger_Ex == nil then
                        DarkDagger_A = true
                    elseif _G.Hop_HallowScryte and _G.Hop_HallowScryte_Ex == nil then
                        Hallow_Scryte_A = true
                    elseif _G.Hop_SpikeyTrident and _G.Hop_SpikeyTrident_Ex == nil then
                        Spikey_Trident_A = true
                    elseif _G.Hop_Yama and _G.Hop_Yama_Ex == nil then
                        Yama_A = true
                    elseif _G.Hop_Raid and _G.Hop_Raid_Ex == nil then
                        AutoRaid = true
                    elseif _G.Hop_Farm_Boss and _G.Hop_Farm_Boss_Ex == nil then
                        Auto_Farm_Boss = true
                    elseif _G.Hop_Farm_All_Boss and _G.Hop_Farm_All_Boss_Ex == nil then
                        Auto_Farm_Boss_All = true
                    elseif _G.Hop_Elite_Hunter and _G.Hop_Elite_Hunter_Ex == nil then
                        EliteHunter = true
                    elseif _G.Hop_Buy_Legendary_Sword and _G.Hop_Buy_Legendary_Sword_Ex == nil then
                        Auto_Buy_Legendary_Sword = true
                    elseif _G.Hop_Bring_Fruit and _G.Hop_Bring_Fruit_Ex == nil then
                        BringFruit = true
                    else
                        HopServer()
                        wait(25)
                    end
                end
            end
        end)
        
        function CheckLevel()
            local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
            if Old_World then
                if Lv == 1 or Lv <= 9 or SelectMonster == "Bandit [Lv. 5]" then -- Bandit
                    Ms = "Bandit [Lv. 5]"
                    NameQuest = "BanditQuest1"
                    QuestLv = 1
                    NameMon = "Bandit"
                    CFrameQ = CFrame.new(1060.9383544922, 16.455066680908, 1547.7841796875)
                    CFrameMon = CFrame.new(1038.5533447266, 41.296249389648, 1576.5098876953)
                elseif Lv == 10 or Lv <= 14 or SelectMonster == "Monkey [Lv. 14]" then -- Monkey
                    Ms = "Monkey [Lv. 14]"
                    NameQuest = "JungleQuest"
                    QuestLv = 1
                    NameMon = "Monkey"
                    CFrameQ = CFrame.new(-1601.6553955078, 36.85213470459, 153.38809204102)
                    CFrameMon = CFrame.new(-1448.1446533203, 50.851993560791, 63.60718536377)
                elseif Lv == 15 or Lv <= 29 or SelectMonster == "Gorilla [Lv. 20]" then -- Gorilla
                    Ms = "Gorilla [Lv. 20]"
                    NameQuest = "JungleQuest"
                    QuestLv = 2
                    NameMon = "Gorilla"
                    CFrameQ = CFrame.new(-1601.6553955078, 36.85213470459, 153.38809204102)
                    CFrameMon = CFrame.new(-1142.6488037109, 40.462348937988, -515.39227294922)
                elseif Lv == 30 or Lv <= 39 or SelectMonster == "Pirate [Lv. 35]" then -- Pirate
                    Ms = "Pirate [Lv. 35]"
                    NameQuest = "BuggyQuest1"
                    QuestLv = 1
                    NameMon = "Pirate"
                    CFrameQ = CFrame.new(-1140.1761474609, 4.752049446106, 3827.4057617188)
                    CFrameMon = CFrame.new(-1201.0881347656, 40.628940582275, 3857.5966796875)
                elseif Lv == 40 or Lv <= 59 or SelectMonster == "Brute [Lv. 45]" then -- Brute
                    Ms = "Brute [Lv. 45]"
                    NameQuest = "BuggyQuest1"
                    QuestLv = 2
                    NameMon = "Brute"
                    CFrameQ = CFrame.new(-1140.1761474609, 4.752049446106, 3827.4057617188)
                    CFrameMon = CFrame.new(-1387.5324707031, 24.592035293579, 4100.9575195313)
                elseif Lv == 60 or Lv <= 74 or SelectMonster == "Desert Bandit [Lv. 60]" then -- Desert Bandit
                    Ms = "Desert Bandit [Lv. 60]"
                    NameQuest = "DesertQuest"
                    QuestLv = 1
                    NameMon = "Desert Bandit"
                    CFrameQ = CFrame.new(896.51721191406, 6.4384617805481, 4390.1494140625)
                    CFrameMon = CFrame.new(984.99896240234, 16.109552383423, 4417.91015625)
                elseif Lv == 75 or Lv <= 89 or SelectMonster == "Desert Officer [Lv. 70]" then -- Desert Officer
                    Ms = "Desert Officer [Lv. 70]"
                    NameQuest = "DesertQuest"
                    QuestLv = 2
                    NameMon = "Desert Officer"
                    CFrameQ = CFrame.new(896.51721191406, 6.4384617805481, 4390.1494140625)
                    CFrameMon = CFrame.new(1547.1510009766, 14.452038764954, 4381.8002929688)
                elseif Lv == 90 or Lv <= 99 or SelectMonster == "Snow Bandit [Lv. 90]" then -- Snow Bandit
                    Ms = "Snow Bandit [Lv. 90]"
                    NameQuest = "SnowQuest"
                    QuestLv = 1
                    NameMon = "Snow Bandit"
                    CFrameQ = CFrame.new(1386.8073730469, 87.272789001465, -1298.3576660156)
                    CFrameMon = CFrame.new(1356.3028564453, 105.76865386963, -1328.2418212891)
                elseif Lv == 100 or Lv <= 119 or SelectMonster == "Snowman [Lv. 100]" then -- Snowman
                    Ms = "Snowman [Lv. 100]"
                    NameQuest = "SnowQuest"
                    QuestLv = 2
                    NameMon = "Snowman"
                    CFrameQ = CFrame.new(1386.8073730469, 87.272789001465, -1298.3576660156)
                    CFrameMon = CFrame.new(1218.7956542969, 138.01184082031, -1488.0262451172)
                elseif Lv == 120 or Lv <= 149 or SelectMonster == "Chief Petty Officer [Lv. 120]" then -- Chief Petty Officer
                    Ms = "Chief Petty Officer [Lv. 120]"
                    NameQuest = "MarineQuest2"
                    QuestLv = 1
                    NameMon = "Chief Petty Officer"
                    CFrameQ = CFrame.new(-5035.49609375, 28.677835464478, 4324.1840820313)
                    CFrameMon = CFrame.new(-4931.1552734375, 65.793113708496, 4121.8393554688)
                elseif Lv == 150 or Lv <= 174 or SelectMonster == "Sky Bandit [Lv. 150]" then -- Sky Bandit
                    Ms = "Sky Bandit [Lv. 150]"
                    NameQuest = "SkyQuest"
                    QuestLv = 1
                    NameMon = "Sky Bandits"
                    CFrameQ = CFrame.new(-4842.1372070313, 717.69543457031, -2623.0483398438)
                    CFrameMon = CFrame.new(-4955.6411132813, 365.46365356445, -2908.1865234375)
                elseif Lv == 175 or Lv <= 249 or SelectMonster == "Dark Master [Lv. 175]" then -- Dark Master
                    Ms = "Dark Master [Lv. 175]"
                    NameQuest = "SkyQuest"
                    QuestLv = 2
                    NameMon = "Dark Master"
                    CFrameQ = CFrame.new(-4842.1372070313, 717.69543457031, -2623.0483398438)
                    CFrameMon = CFrame.new(-5148.1650390625, 439.04571533203, -2332.9611816406)
                elseif Lv == 250 or Lv <= 274 or SelectMonster == "Toga Warrior [Lv. 250]" then -- Toga Warrior
                    Ms = "Toga Warrior [Lv. 250]"
                    NameQuest = "ColosseumQuest"
                    QuestLv = 1
                    NameMon = "Toga Warrior"
                    CFrameQ = CFrame.new(-1577.7890625, 7.4151420593262, -2984.4838867188)
                    CFrameMon = CFrame.new(-1872.5166015625, 49.080215454102, -2913.810546875)
                elseif Lv == 275 or Lv <= 299 or SelectMonster == "Gladiator [Lv. 275]" then -- Gladiator
                    Ms = "Gladiator [Lv. 275]"
                    NameQuest = "ColosseumQuest"
                    QuestLv = 2
                    NameMon = "Gladiator"
                    CFrameQ = CFrame.new(-1577.7890625, 7.4151420593262, -2984.4838867188)
                    CFrameMon = CFrame.new(-1521.3740234375, 81.203170776367, -3066.3139648438)
                elseif Lv == 300 or Lv <= 329 or SelectMonster == "Military Soldier [Lv. 300]" then -- Military Soldier
                    Ms = "Military Soldier [Lv. 300]"
                    NameQuest = "MagmaQuest"
                    QuestLv = 1
                    NameMon = "Military Soldier"
                    CFrameQ = CFrame.new(-5316.1157226563, 12.262831687927, 8517.00390625)
                    CFrameMon = CFrame.new(-5369.0004882813, 61.24352645874, 8556.4921875)
                elseif Lv == 330 or Lv <= 374 or SelectMonster == "Military Spy [Lv. 325]" then -- Military Spy
                    Ms = "Military Spy [Lv. 325]"
                    NameQuest = "MagmaQuest"
                    QuestLv = 2
                    NameMon = "Military Spy"
                    CFrameQ = CFrame.new(-5316.1157226563, 12.262831687927, 8517.00390625)
                    CFrameMon = CFrame.new(-5984.0532226563, 82.14656829834, 8753.326171875)
                elseif Lv == 375 or Lv <= 399 or SelectMonster == "Fishman Warrior [Lv. 375]" then -- Fishman Warrior 
                    _G.FM = true
                    Ms = "Fishman Warrior [Lv. 375]"
                    NameQuest = "FishmanQuest"
                    QuestLv = 1
                    NameMon = "Fishman Warrior"
                    CFrameQ = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
                    CFrameMon = CFrame.new(60844.10546875, 98.462875366211, 1298.3985595703)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
                    end
                elseif Lv == 400 or Lv <= 449 or SelectMonster == "Fishman Commando [Lv. 400]" then -- Fishman Commando
                    _G.FM = true
                    Ms = "Fishman Commando [Lv. 400]"
                    NameQuest = "FishmanQuest"
                    QuestLv = 2
                    NameMon = "Fishman Commando"
                    CFrameQ = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
                    CFrameMon = CFrame.new(61738.3984375, 64.207321166992, 1433.8375244141)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
                    end
                elseif Lv == 450 or Lv <= 474 or SelectMonster == "God's Guard [Lv. 450]" then -- God's Guard
                    _G.FM = false
                    Ms = "God's Guard [Lv. 450]"
                    NameQuest = "SkyExp1Quest"
                    QuestLv = 1
                    NameMon = "God's Guard"
                    CFrameQ = CFrame.new(-4721.8603515625, 845.30297851563, -1953.8489990234)
                    CFrameMon = CFrame.new(-4628.0498046875, 866.92877197266, -1931.2352294922)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
                    end
                elseif Lv == 475 or Lv <= 524 or SelectMonster == "Shanda [Lv. 475]" then -- Shanda
                    _G.FM = false
                    Ms = "Shanda [Lv. 475]"
                    NameQuest = "SkyExp1Quest"
                    QuestLv = 2
                    NameMon = "Shanda"
                    CFrameQ = CFrame.new(-7863.1596679688, 5545.5190429688, -378.42266845703)
                    CFrameMon = CFrame.new(-7685.1474609375, 5601.0751953125, -441.38876342773)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
                    end
                elseif Lv == 525 or Lv <= 549 or SelectMonster == "Royal Squad [Lv. 525]" then -- Royal Squad
                    Ms = "Royal Squad [Lv. 525]"
                    NameQuest = "SkyExp2Quest"
                    QuestLv = 1
                    NameMon = "Royal Squad"
                    CFrameQ = CFrame.new(-7903.3828125, 5635.9897460938, -1410.923828125)
                    CFrameMon = CFrame.new(-7654.2514648438, 5637.1079101563, -1407.7550048828)
                elseif Lv == 550 or Lv <= 624 or SelectMonster == "Royal Soldier [Lv. 550]" then -- Royal Soldier
                    Ms = "Royal Soldier [Lv. 550]"
                    NameQuest = "SkyExp2Quest"
                    QuestLv = 2
                    NameMon = "Royal Soldier"
                    CFrameQ = CFrame.new(-7903.3828125, 5635.9897460938, -1410.923828125)
                    CFrameMon = CFrame.new(-7760.4106445313, 5679.9077148438, -1884.8112792969)
                elseif Lv == 625 or Lv <= 649 or SelectMonster == "Galley Pirate [Lv. 625]" then -- Galley Pirate
                    Ms = "Galley Pirate [Lv. 625]"
                    NameQuest = "FountainQuest"
                    QuestLv = 1
                    NameMon = "Galley Pirate"
                    CFrameQ = CFrame.new(5258.2788085938, 38.526931762695, 4050.044921875)
                    CFrameMon = CFrame.new(5557.1684570313, 152.32717895508, 3998.7758789063)
                elseif Lv >= 650 or SelectMonster == "Galley Captain [Lv. 650]" then -- Galley Captain
                    Ms = "Galley Captain [Lv. 650]"
                    NameQuest = "FountainQuest"
                    QuestLv = 2
                    NameMon = "Galley Captain"
                    CFrameQ = CFrame.new(5258.2788085938, 38.526931762695, 4050.044921875)
                    CFrameMon = CFrame.new(5677.6772460938, 92.786109924316, 4966.6323242188)
                end
            end
            if New_World then
                if Lv == 700 or Lv <= 724 or SelectMonster == "Raider [Lv. 700]" then -- Raider
                    Ms = "Raider [Lv. 700]"
                    NameQuest = "Area1Quest"
                    QuestLv = 1
                    NameMon = "Raider"
                    CFrameQ = CFrame.new(-427.72567749023, 72.99634552002, 1835.9426269531)
                    CFrameMon = CFrame.new(68.874565124512, 93.635643005371, 2429.6752929688)
                elseif Lv == 725 or Lv <= 774 or SelectMonster == "Mercenary [Lv. 725]" then -- Mercenary
                    Ms = "Mercenary [Lv. 725]"
                    NameQuest = "Area1Quest"
                    QuestLv = 2
                    NameMon = "Mercenary"
                    CFrameQ = CFrame.new(-427.72567749023, 72.99634552002, 1835.9426269531)
                    CFrameMon = CFrame.new(-864.85009765625, 122.47104644775, 1453.1505126953)
                elseif Lv == 775 or Lv <= 799 or SelectMonster == "Swan Pirate [Lv. 775]" then -- Swan Pirate
                    Ms = "Swan Pirate [Lv. 775]"
                    NameQuest = "Area2Quest"
                    QuestLv = 1
                    NameMon = "Swan Pirate"
                    CFrameQ = CFrame.new(635.61151123047, 73.096351623535, 917.81298828125)
                    CFrameMon = CFrame.new(1065.3669433594, 137.64012145996, 1324.3798828125)
                elseif Lv == 800 or Lv <= 874 or SelectMonster == "Factory Staff [Lv. 800]" then -- Factory Staff
                    Ms = "Factory Staff [Lv. 800]"
                    NameQuest = "Area2Quest"
                    QuestLv = 2
                    NameMon = "Factory Staff"
                    CFrameQ = CFrame.new(635.61151123047, 73.096351623535, 917.81298828125)
                    CFrameMon = CFrame.new(533.22045898438, 128.46876525879, 355.62615966797)
                elseif Lv == 875 or Lv <= 899 or SelectMonster == "Marine Lieutenant [Lv. 875]" then -- Marine Lieutenant
                    Ms = "Marine Lieutenant [Lv. 875]"
                    NameQuest = "MarineQuest3"
                    QuestLv = 1
                    NameMon = "Marine Lieutenant"
                    CFrameQ = CFrame.new(-2440.9934082031, 73.04190826416, -3217.7082519531)
                    CFrameMon = CFrame.new(-2489.2622070313, 84.613594055176, -3151.8830566406)
                elseif Lv == 900 or Lv <= 949 or SelectMonster == "Marine Captain [Lv. 900]" then -- Marine Captain
                    Ms = "Marine Captain [Lv. 900]"
                    NameQuest = "MarineQuest3"
                    QuestLv = 2
                    NameMon = "Marine Captain"
                    CFrameQ = CFrame.new(-2440.9934082031, 73.04190826416, -3217.7082519531)
                    CFrameMon = CFrame.new(-2335.2026367188, 79.786659240723, -3245.8674316406)
                elseif Lv == 950 or Lv <= 974 or SelectMonster == "Zombie [Lv. 950]" then -- Zombie
                    Ms = "Zombie [Lv. 950]"
                    NameQuest = "ZombieQuest"
                    QuestLv = 1
                    NameMon = "Zombie"
                    CFrameQ = CFrame.new(-5494.3413085938, 48.505931854248, -794.59094238281)
                    CFrameMon = CFrame.new(-5536.4970703125, 101.08577728271, -835.59075927734)
                elseif Lv == 975 or Lv <= 999 or SelectMonster == "Vampire [Lv. 975]" then -- Vampire
                    Ms = "Vampire [Lv. 975]"
                    NameQuest = "ZombieQuest"
                    QuestLv = 2
                    NameMon = "Vampire"
                    CFrameQ = CFrame.new(-5494.3413085938, 48.505931854248, -794.59094238281)
                    CFrameMon = CFrame.new(-5806.1098632813, 16.722528457642, -1164.4384765625)
                elseif Lv == 1000 or Lv <= 1049 or SelectMonster == "Snow Trooper [Lv. 1000]" then -- Snow Trooper
                    Ms = "Snow Trooper [Lv. 1000]"
                    NameQuest = "SnowMountainQuest"
                    QuestLv = 1
                    NameMon = "Snow Trooper"
                    CFrameQ = CFrame.new(607.05963134766, 401.44781494141, -5370.5546875)
                    CFrameMon = CFrame.new(535.21051025391, 432.74209594727, -5484.9165039063)
                elseif Lv == 1050 or Lv <= 1099 or SelectMonster == "Winter Warrior [Lv. 1050]" then -- Winter Warrior
                    Ms = "Winter Warrior [Lv. 1050]"
                    NameQuest = "SnowMountainQuest"
                    QuestLv = 2
                    NameMon = "Winter Warrior"
                    CFrameQ = CFrame.new(607.05963134766, 401.44781494141, -5370.5546875)
                    CFrameMon = CFrame.new(1234.4449462891, 456.95419311523, -5174.130859375)
                elseif Lv == 1100 or Lv <= 1124 or SelectMonster == "Lab Subordinate [Lv. 1100]" then -- Lab Subordinate
                    Ms = "Lab Subordinate [Lv. 1100]"
                    NameQuest = "IceSideQuest"
                    QuestLv = 1
                    NameMon = "Lab Subordinate"
                    CFrameQ = CFrame.new(-6061.841796875, 15.926671981812, -4902.0385742188)
                    CFrameMon = CFrame.new(-5720.5576171875, 63.309471130371, -4784.6103515625)
                elseif Lv == 1125 or Lv <= 1174 or SelectMonster == "Horned Warrior [Lv. 1125]" then -- Horned Warrior
                    Ms = "Horned Warrior [Lv. 1125]"
                    NameQuest = "IceSideQuest"
                    QuestLv = 2
                    NameMon = "Horned Warrior"
                    CFrameQ = CFrame.new(-6061.841796875, 15.926671981812, -4902.0385742188)
                    CFrameMon = CFrame.new(-6292.751953125, 91.181983947754, -5502.6499023438)
                elseif Lv == 1175 or Lv <= 1199 or SelectMonster == "Magma Ninja [Lv. 1175]" then -- Magma Ninja
                    Ms = "Magma Ninja [Lv. 1175]"
                    NameQuest = "FireSideQuest"
                    QuestLv = 1
                    NameMon = "Magma Ninja"
                    CFrameQ = CFrame.new(-5429.0473632813, 15.977565765381, -5297.9614257813)
                    CFrameMon = CFrame.new(-5461.8388671875, 130.36347961426, -5836.4702148438)
                elseif Lv == 1200 or Lv <= 1249 or SelectMonster == "Lava Pirate [Lv. 1200]" then -- Lava Pirate
                    Ms = "Lava Pirate [Lv. 1200]"
                    NameQuest = "FireSideQuest"
                    QuestLv = 2
                    NameMon = "Lava Pirate"
                    CFrameQ = CFrame.new(-5429.0473632813, 15.977565765381, -5297.9614257813)
                    CFrameMon = CFrame.new(-5251.1889648438, 55.164535522461, -4774.4096679688)
                elseif Lv == 1250 or Lv <= 1274 or SelectMonster == "Ship Deckhand [Lv. 1250]" then -- Ship Deckhand
                    Ms = "Ship Deckhand [Lv. 1250]"
                    NameQuest = "ShipQuest1"
                    QuestLv = 1
                    NameMon = "Ship Deckhand"
                    CFrameQ = CFrame.new(1040.2927246094, 125.08293151855, 32911.0390625)
                    CFrameMon = CFrame.new(921.12365722656, 125.9839553833, 33088.328125)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                    end
                elseif Lv == 1275 or Lv <= 1299 or SelectMonster == "Ship Engineer [Lv. 1275]" then -- Ship Engineer
                    Ms = "Ship Engineer [Lv. 1275]"
                    NameQuest = "ShipQuest1"
                    QuestLv = 2
                    NameMon = "Ship Engineer"
                    CFrameQ = CFrame.new(1040.2927246094, 125.08293151855, 32911.0390625)
                    CFrameMon = CFrame.new(886.28179931641, 40.47790145874, 32800.83203125)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                    end
                elseif Lv == 1300 or Lv <= 1324 or SelectMonster == "Ship Steward [Lv. 1300]" then -- Ship Steward
                    Ms = "Ship Steward [Lv. 1300]"
                    NameQuest = "ShipQuest2"
                    QuestLv = 1
                    NameMon = "Ship Steward"
                    CFrameQ = CFrame.new(971.42065429688, 125.08293151855, 33245.54296875)
                    CFrameMon = CFrame.new(943.85504150391, 129.58183288574, 33444.3671875)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                    end
                elseif Lv == 1325 or Lv <= 1349 or SelectMonster == "Ship Officer [Lv. 1325]" then -- Ship Officer
                    Ms = "Ship Officer [Lv. 1325]"
                    NameQuest = "ShipQuest2"
                    QuestLv = 2
                    NameMon = "Ship Officer"
                    CFrameQ = CFrame.new(971.42065429688, 125.08293151855, 33245.54296875)
                    CFrameMon = CFrame.new(955.38458251953, 181.08335876465, 33331.890625)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                    end
                elseif Lv == 1350 or Lv <= 1374 or SelectMonster == "Arctic Warrior [Lv. 1350]" then -- Arctic Warrior
                    Ms = "Arctic Warrior [Lv. 1350]"
                    NameQuest = "FrostQuest"
                    QuestLv = 1
                    NameMon = "Arctic Warrior"
                    CFrameQ = CFrame.new(5668.1372070313, 28.202531814575, -6484.6005859375)
                    CFrameMon = CFrame.new(5935.4541015625, 77.26016998291, -6472.7568359375)
                    if Auto_Farm and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
                    end
                elseif Lv == 1375 or Lv <= 1424 or SelectMonster == "Snow Lurker [Lv. 1375]" then -- Snow Lurker
                    Ms = "Snow Lurker [Lv. 1375]"
                    NameQuest = "FrostQuest"
                    QuestLv = 2
                    NameMon = "Snow Lurker"
                    CFrameQ = CFrame.new(5668.1372070313, 28.202531814575, -6484.6005859375)
                    CFrameMon = CFrame.new(5628.482421875, 57.574996948242, -6618.3481445313)
                elseif Lv == 1425 or Lv <= 1449 or SelectMonster == "Sea Soldier [Lv. 1425]" then -- Sea Soldier
                    Ms = "Sea Soldier [Lv. 1425]"
                    NameQuest = "ForgottenQuest"
                    QuestLv = 1
                    NameMon = "Sea Soldier"
                    CFrameQ = CFrame.new(-3054.5827636719, 236.87213134766, -10147.790039063)
                    CFrameMon = CFrame.new(-3185.0153808594, 58.789089202881, -9663.6064453125)
                elseif Lv >= 1450 or SelectMonster == "Water Fighter [Lv. 1450]" then -- Water Fighter
                    Ms = "Water Fighter [Lv. 1450]"
                    NameQuest = "ForgottenQuest"
                    QuestLv = 2
                    NameMon = "Water Fighter"
                    CFrameQ = CFrame.new(-3054.5827636719, 236.87213134766, -10147.790039063)
                    CFrameMon = CFrame.new(-3262.9301757813, 298.69036865234, -10552.529296875)
                end
            end
            if Three_World then
                if Lv == 1500 or Lv <= 1524 or SelectMonster == "Pirate Millionaire [Lv. 1500]" then -- Pirate Millionaire
                    Ms = "Pirate Millionaire [Lv. 1500]"
                    NameQuest = "PiratePortQuest"
                    QuestLv = 1
                    NameMon = "Pirate Millionaire"
                    CFrameQ = CFrame.new(-289.61752319336, 43.819011688232, 5580.0903320313)
                    CFrameMon = CFrame.new(-435.68109130859, 189.69866943359, 5551.0756835938)
                elseif Lv == 1525 or Lv <= 1574 or SelectMonster == "Pistol Billionaire [Lv. 1525]" then -- Pistol Billoonaire
                    Ms = "Pistol Billionaire [Lv. 1525]"
                    NameQuest = "PiratePortQuest"
                    QuestLv = 2
                    NameMon = "Pistol Billionaire"
                    CFrameQ = CFrame.new(-289.61752319336, 43.819011688232, 5580.0903320313)
                    CFrameMon = CFrame.new(-236.53652954102, 217.46676635742, 6006.0883789063)
                elseif Lv == 1575 or Lv <= 1599 or SelectMonster == "Dragon Crew Warrior [Lv. 1575]" then -- Dragon Crew Warrior
                    Ms = "Dragon Crew Warrior [Lv. 1575]"
                    NameQuest = "AmazonQuest"
                    QuestLv = 1
                    NameMon = "Dragon Crew Warrior"
                    CFrameQ = CFrame.new(5833.1147460938, 51.60498046875, -1103.0693359375)
                    CFrameMon = CFrame.new(6301.9975585938, 104.77153015137, -1082.6075439453)
                elseif Lv == 1600 or Lv <= 1624 or SelectMonster == "Dragon Crew Archer [Lv. 1600]" then -- Dragon Crew Archer
                    Ms = "Dragon Crew Archer [Lv. 1600]"
                    NameQuest = "AmazonQuest"
                    QuestLv = 2
                    NameMon = "Dragon Crew Archer"
                    CFrameQ = CFrame.new(5833.1147460938, 51.60498046875, -1103.0693359375)
                    CFrameMon = CFrame.new(6831.1171875, 441.76708984375, 446.58615112305)
                elseif Lv == 1625 or Lv <= 1649 or SelectMonster == "Female Islander [Lv. 1625]" then -- Female Islander
                    Ms = "Female Islander [Lv. 1625]"
                    NameQuest = "AmazonQuest2"
                    QuestLv = 1
                    NameMon = "Female Islander"
                    CFrameQ = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
                    CFrameMon = CFrame.new(5792.5166015625, 848.14392089844, 1084.1818847656)
                elseif Lv == 1650 or Lv <= 1699 or SelectMonster == "Giant Islander [Lv. 1650]" then -- Giant Islander
                    Ms = "Giant Islander [Lv. 1650]"
                    NameQuest = "AmazonQuest2"
                    QuestLv = 2
                    NameMon = "Giant Islander"
                    CFrameQ = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
                    CFrameMon = CFrame.new(5009.5068359375, 664.11071777344, -40.960144042969)
                elseif Lv == 1700 or Lv <= 1724 or SelectMonster == "Marine Commodore [Lv. 1700]" then -- Marine Commodore
                    Ms = "Marine Commodore [Lv. 1700]"
                    NameQuest = "MarineTreeIsland"
                    QuestLv = 1
                    NameMon = "Marine Commodore"
                    CFrameQ = CFrame.new(2179.98828125, 28.731239318848, -6740.0551757813)
                    CFrameMon = CFrame.new(2198.0063476563, 128.71075439453, -7109.5043945313)
                elseif Lv == 1725 or Lv <= 1774 or SelectMonster == "Marine Rear Admiral [Lv. 1725]" then -- Marine Rear Admiral
                    Ms = "Marine Rear Admiral [Lv. 1725]"
                    NameQuest = "MarineTreeIsland"
                    QuestLv = 2
                    NameMon = "Marine Rear Admiral"
                    CFrameQ = CFrame.new(2179.98828125, 28.731239318848, -6740.0551757813)
                    CFrameMon = CFrame.new(3294.3142089844, 385.41125488281, -7048.6342773438)
                elseif Lv == 1775 or Lv <= 1799 or SelectMonster == "Fishman Raider [Lv. 1775]" then -- Fishman Raide
                    Ms = "Fishman Raider [Lv. 1775]"
                    NameQuest = "DeepForestIsland3"
                    QuestLv = 1
                    NameMon = "Fishman Raider"
                    CFrameQ = CFrame.new(-10582.759765625, 331.78845214844, -8757.666015625)
                    CFrameMon = CFrame.new(-10553.268554688, 521.38439941406, -8176.9458007813)
                elseif Lv == 1800 or Lv <= 1824 or SelectMonster == "Fishman Captain [Lv. 1800]" then -- Fishman Captain
                    Ms = "Fishman Captain [Lv. 1800]"
                    NameQuest = "DeepForestIsland3"
                    QuestLv = 2
                    NameMon = "Fishman Captain"
                    CFrameQ = CFrame.new(-10583.099609375, 331.78845214844, -8759.4638671875)
                    CFrameMon = CFrame.new(-10789.401367188, 427.18637084961, -9131.4423828125)
                elseif Lv == 1825 or Lv <= 1849 or SelectMonster == "Forest Pirate [Lv. 1825]" then -- Forest Pirate
                    Ms = "Forest Pirate [Lv. 1825]"
                    NameQuest = "DeepForestIsland"
                    QuestLv = 1
                    NameMon = "Forest Pirate"
                    CFrameQ = CFrame.new(-13232.662109375, 332.40396118164, -7626.4819335938)
                    CFrameMon = CFrame.new(-13489.397460938, 400.30349731445, -7770.251953125)
                elseif Lv == 1850 or Lv <= 1899 or SelectMonster == "Mythological Pirate [Lv. 1850]" then -- Mythological Pirate
                    Ms = "Mythological Pirate [Lv. 1850]"
                    NameQuest = "DeepForestIsland"
                    QuestLv = 2
                    NameMon = "Mythological Pirate"
                    CFrameQ = CFrame.new(-13232.662109375, 332.40396118164, -7626.4819335938)
                    CFrameMon = CFrame.new(-13508.616210938, 582.46228027344, -6985.3037109375)
                elseif Lv >= 1900 and Lv <= 1924 or SelectMonster == "Jungle Pirate [Lv. 1900]" then -- Jungle Pirate
                    Ms = "Jungle Pirate [Lv. 1900]"
                    NameQuest = "DeepForestIsland2"
                    QuestLv = 1
                    NameMon = "Jungle Pirate"
                    CFrameQ = CFrame.new(-12682.096679688, 390.88653564453, -9902.1240234375)
                    CFrameMon = CFrame.new(-12267.103515625, 459.75262451172, -10277.200195313)
                elseif Lv >= 1925 and Lv <= 1974 or SelectMonster == "Musketeer Pirate [Lv. 1925]" then -- Musketeer Pirate
                    Ms = "Musketeer Pirate [Lv. 1925]"
                    NameQuest = "DeepForestIsland2"
                    QuestLv = 2
                    NameMon = "Musketeer Pirate"
                    CFrameQ = CFrame.new(-12682.096679688, 390.88653564453, -9902.1240234375)
                    CFrameMon = CFrame.new(-13291.5078125, 520.47338867188, -9904.638671875)
                elseif Lv >= 1975 and Lv <= 1999 or SelectMonster == "Musketeer Pirate [Lv. 1925]" then -- Reborn Skeleton
                    Ms = "Musketeer Pirate [Lv. 1925]"
                    NameQuest = "DeepForestIsland2"
                    QuestLv = 2
                    NameMon = "Musketeer Pirate"
                    CFrameQ = CFrame.new(-12682.096679688, 390.88653564453, -9902.1240234375)
                    CFrameMon = CFrame.new(-13291.5078125, 520.47338867188, -9904.638671875)
                elseif Lv >= 2000 and Lv <= 2024 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Living Zombie
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2025 and Lv <= 2049 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Demonic Soul
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2050 and Lv <= 2074 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Posessed Mummy
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2075 and Lv <= 2099 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Peanut Scout
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2100 and Lv <= 2124 or SelectMonster == "Living Zombie [Lv. 2000]" then -- Peanut President
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2125 and Lv <= 2149 or SelectMonster == "Living Zombie [Lv. 2000]" then --Ice Cream Chef
                    Ms = "Living Zombie [Lv. 2000]"
                    NameQuest = "HauntedQuest1"
                    QuestLv = 2
                    NameMon = "Living Zombie"
                    CFrameQ = CFrame.new(-9480.80762, 142.130661, 5566.37305)
                    CFrameMon = CFrame.new(-10103.7529, 238.565979, 6179.75977)
                elseif Lv >= 2150 and Lv <= 2200 or SelectMonster == "Ice Cream Commander [Lv. 2150]" then -- Ice Cream Commander
                    Ms = "Ice Cream Commander [Lv. 2150]"
                    NameQuest = "IceCreamIslandQuest"
                    QuestLv = 2
                    NameMon = "Ice Cream Commanders"
                    CFrameQ = CFrame.new(-821.35913085938, 65.845329284668, -10965.2578125)
                    CFrameMon = CFrame.new(-697.65338134766, 174.48368835449, -11218.38671875)
                elseif Lv >= 2200 and Lv <= 2250 or SelectMonster == "Ice Cream Commander [Lv. 2150]" then -- Ice Cream Commander
                    Ms = "Cookie Crafter [Lv. 2200]"
                    NameQuest = "CakeQuest1"
                    QuestLv = 1
                    NameMon = "Cookie Crafters"
                    CFrameQ = CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)
                    CFrameMon = CFrame.new(-2358.5791015625, 36.85615539550781, -12111.052734375)
                elseif Lv >= 2225 or SelectMonster == "Cake Guard [Lv. 2225]" then
                    Ms = "Cake Guard [Lv. 2225]"
                    NameQuest = "CakeQuest1"
                    QuestLv = 2
                    NameMon = "Cake Guards"
                    CFrameMon = CFrame.new(-1430.4925537109375, 36.85621643066406, -12322.162109375)
                    CFrameQ = CFrame.new(-2017.4874267578125, 36.85276412963867, -12027.53515625)
                end
            end
        end
        
        function CheckQuestBoss()
            -- Old World
                if _G.SelectBoss == "Saber Expert [Lv. 200] [Boss]" then
                    MsBoss = "Saber Expert [Lv. 200] [Boss]"
                    NameBoss = "Saber Expert"
                    CFrameBoss = CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094)
                elseif _G.SelectBoss == "The Saw [Lv. 100] [Boss]" then
                    MsBoss = "The Saw [Lv. 100] [Boss]"
                    NameBoss = "The Saw"
                    CFrameBoss = CFrame.new(-683.519897, 13.8534927, 1610.87854, -0.290192783, 6.88365773e-08, 0.956968188, 6.98413629e-08, 1, -5.07531119e-08, -0.956968188, 5.21077759e-08, -0.290192783)
                elseif _G.SelectBoss == "Greybeard [Lv. 750] [Raid Boss]" then
                    MsBoss = "Greybeard [Lv. 750] [Raid Boss]"
                    NameBoss = "Greybeard"
                    CFrameBoss = CFrame.new(-4955.72949, 80.8163834, 4305.82666, -0.433646321, -1.03394289e-08, 0.901083171, -3.0443168e-08, 1, -3.17633075e-09, -0.901083171, -2.88092288e-08, -0.433646321)
                elseif _G.SelectBoss == "The Gorilla King [Lv. 25] [Boss]" then
                    MsBoss = "The Gorilla King [Lv. 25] [Boss]"
                    NameBoss = "The Gorilla King"
                    NameQuestBoss = "JungleQuest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
                    CFrameBoss = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
                elseif _G.SelectBoss == "Bobby [Lv. 55] [Boss]" then
                    MsBoss = "Bobby [Lv. 55] [Boss]"
                    NameBoss = "Bobby"
                    NameQuestBoss = "BuggyQuest1"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
                    CFrameBoss = CFrame.new(-1147.65173, 32.5966301, 4156.02588, 0.956680477, -1.77109952e-10, -0.29113996, 5.16530874e-10, 1, 1.08897802e-09, 0.29113996, -1.19218679e-09, 0.956680477)
                elseif _G.SelectBoss == "Yeti [Lv. 110] [Boss]" then
                    MsBoss = "Yeti [Lv. 110] [Boss]"
                    NameBoss = "Yeti"
                    NameQuestBoss = "SnowQuest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(1384.90247, 87.3078308, -1296.6825, 0.280209213, 2.72035177e-08, -0.959938943, -6.75690828e-08, 1, 8.6151708e-09, 0.959938943, 6.24481444e-08, 0.280209213)
                    CFrameBoss = CFrame.new(1221.7356, 138.046906, -1488.84082, 0.349343032, -9.49245944e-08, 0.936994851, 6.29478194e-08, 1, 7.7838429e-08, -0.936994851, 3.17894653e-08, 0.349343032)
                elseif _G.SelectBoss == "Mob Leader [Lv. 120] [Boss]" then
                    MsBoss = "Mob Leader [Lv. 120] [Boss]"
                    NameBoss = "Mob Leader"
                    CFrameBoss = CFrame.new(-2848.59399, 7.4272871, 5342.44043, -0.928248107, -8.7248246e-08, 0.371961564, -7.61816636e-08, 1, 4.44474857e-08, -0.371961564, 1.29216433e-08, -0.92824)
                elseif _G.SelectBoss == "Vice Admiral [Lv. 130] [Boss]" then
                    MsBoss = "Vice Admiral [Lv. 130] [Boss]"
                    NameBoss = "Vice Admiral"
                    NameQuestBoss = "MarineQuest2"
                    LevelQuestBoss = 2
                    CFrameQuestBoss = CFrame.new(-5035.42285, 28.6520386, 4324.50293, -0.0611100644, -8.08395768e-08, 0.998130739, -1.57416586e-08, 1, 8.00271849e-08, -0.998130739, -1.08217701e-08, -0.0611100644)
                    CFrameBoss = CFrame.new(-5078.45898, 99.6520691, 4402.1665, -0.555574954, -9.88630566e-11, 0.831466436, -6.35508286e-08, 1, -4.23449258e-08, -0.831466436, -7.63661632e-08, -0.555574954)
                elseif _G.SelectBoss == "Warden [Lv. 175] [Boss]" then
                    MsBoss = "Warden [Lv. 175] [Boss]"
                    NameBoss = "Warden"
                    NameQuestBoss = "ImpelQuest"
                    LevelQuestBoss = 1
                    CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
                    CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
                elseif _G.SelectBoss == "Chief Warden [Lv. 200] [Boss]" then
                    MsBoss = "Chief Warden [Lv. 200] [Boss]"
                    NameBoss = "Chief Warden"
                    NameQuestBoss = "ImpelQuest"
                    LevelQuestBoss = 2
                    CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
                    CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
                elseif _G.SelectBoss == "Swan [Lv. 225] [Boss]" then
                    MsBoss = "Swan [Lv. 225] [Boss]"
                    NameBoss = "Swan"
                    NameQuestBoss = "ImpelQuest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
                    CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
                elseif _G.SelectBoss == "Magma Admiral [Lv. 350] [Boss]" then
                    MsBoss = "Magma Admiral [Lv. 350] [Boss]"
                    NameBoss = "Magma Admiral"
                    NameQuestBoss = "MagmaQuest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-5317.07666, 12.2721891, 8517.41699, 0.51175487, -2.65508806e-08, -0.859131515, -3.91131572e-08, 1, -5.42026761e-08, 0.859131515, 6.13418294e-08, 0.51175487)
                    CFrameBoss = CFrame.new(-5530.12646, 22.8769703, 8859.91309, 0.857838571, 2.23414389e-08, 0.513919294, 1.53689133e-08, 1, -6.91265853e-08, -0.513919294, 6.71978384e-08, 0.857838571)
                elseif _G.SelectBoss == "Fishman Lord [Lv. 425] [Boss]" then
                    MsBoss = "Fishman Lord [Lv. 425] [Boss]"
                    NameBoss = "Fishman Lord"
                    NameQuestBoss = "FishmanQuest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(61123.0859, 18.5066795, 1570.18018, 0.927145958, 1.0624845e-07, 0.374700129, -6.98219367e-08, 1, -1.10790765e-07, -0.374700129, 7.65569368e-08, 0.927145958)
                    CFrameBoss = CFrame.new(61351.7773, 31.0306778, 1113.31409, 0.999974668, 0, -0.00714713801, 0, 1.00000012, 0, 0.00714714266, 0, 0.999974549)
                elseif _G.SelectBoss == "Wysper [Lv. 500] [Boss]" then
                    MsBoss = "Wysper [Lv. 500] [Boss]"
                    NameBoss = "Wysper"
                    NameQuestBoss = "SkyExp1Quest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-7862.94629, 5545.52832, -379.833954, 0.462944925, 1.45838088e-08, -0.886386991, 1.0534996e-08, 1, 2.19553424e-08, 0.886386991, -1.95022007e-08, 0.462944925)
                    CFrameBoss = CFrame.new(-7925.48389, 5550.76074, -636.178345, 0.716468513, -1.22915289e-09, 0.697619379, 3.37381434e-09, 1, -1.70304748e-09, -0.697619379, 3.57381835e-09, 0.716468513)
                elseif _G.SelectBoss == "Thunder God [Lv. 575] [Boss]" then
                    MsBoss = "Thunder God [Lv. 575] [Boss]"
                    NameBoss = "Thunder God"
                    NameQuestBoss = "SkyExp2Quest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-7902.78613, 5635.99902, -1411.98706, -0.0361216255, -1.16895912e-07, 0.999347389, 1.44533963e-09, 1, 1.17024491e-07, -0.999347389, 5.6715117e-09, -0.0361216255)
                    CFrameBoss = CFrame.new(-7917.53613, 5616.61377, -2277.78564, 0.965189934, 4.80563429e-08, -0.261550069, -6.73089886e-08, 1, -6.46515304e-08, 0.261550069, 8.00056768e-08, 0.965189934)
                elseif _G.SelectBoss == "Cyborg [Lv. 675] [Boss]" then
                    MsBoss = "Cyborg [Lv. 675] [Boss]"
                    NameBoss = "Cyborg"
                    NameQuestBoss = "FountainQuest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(5253.54834, 38.5361786, 4050.45166, -0.0112687312, -9.93677887e-08, -0.999936521, 2.55291371e-10, 1, -9.93769547e-08, 0.999936521, -1.37512213e-09, -0.0112687312)
                    CFrameBoss = CFrame.new(6041.82813, 52.7112198, 3907.45142, -0.563162148, 1.73805248e-09, -0.826346457, -5.94632716e-08, 1, 4.26280238e-08, 0.826346457, 7.31437524e-08, -0.563162148)
                -- New World
                elseif _G.SelectBoss == "Diamond [Lv. 750] [Boss]" then
                    MsBoss = "Diamond [Lv. 750] [Boss]"
                    NameBoss = "Diamond"
                    NameQuestBoss = "Area1Quest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
                    CFrameBoss = CFrame.new(-1736.26587, 198.627731, -236.412857, -0.997808516, 0, -0.0661673471, 0, 1, 0, 0.0661673471, 0, -0.997808516)
                elseif _G.SelectBoss == "Jeremy [Lv. 850] [Boss]" then
                    MsBoss = "Jeremy [Lv. 850] [Boss]"
                    NameBoss = "Jeremy"
                    NameQuestBoss = "Area2Quest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
                    CFrameBoss = CFrame.new(2203.76953, 448.966034, 752.731079, -0.0217453763, 0, -0.999763548, 0, 1, 0, 0.999763548, 0, -0.0217453763)
                elseif _G.SelectBoss == "Fajita [Lv. 925] [Boss]" then
                    MsBoss = "Fajita [Lv. 925] [Boss]"
                    NameBoss = "Fajita"
                    NameQuestBoss = "MarineQuest3"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
                    CFrameBoss = CFrame.new(-2297.40332, 115.449463, -3946.53833, 0.961227536, -1.46645796e-09, -0.275756449, -2.3212845e-09, 1, -1.34094433e-08, 0.275756449, 1.35296352e-08, 0.961227536)
                elseif _G.SelectBoss == "Don Swan [Lv. 1000] [Boss]" then
                    MsBoss = "Don Swan [Lv. 1000] [Boss]"
                    NameBoss = "Don Swan"
                    CFrameBoss = CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072)
                elseif _G.SelectBoss == "Smoke Admiral [Lv. 1150] [Boss]" then
                    MsBoss = "Smoke Admiral [Lv. 1150] [Boss]"
                    NameBoss = "Smoke Admiral"
                    NameQuestBoss = "IceSideQuest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-6059.96191, 15.9868021, -4904.7373, -0.444992423, -3.0874483e-09, 0.895534337, -3.64098796e-08, 1, -1.4644522e-08, -0.895534337, -3.91229982e-08, -0.444992423)
                    CFrameBoss = CFrame.new(-5115.72754, 23.7664986, -5338.2207, 0.251453817, 1.48345061e-08, -0.967869282, 4.02796978e-08, 1, 2.57916977e-08, 0.967869282, -4.54708946e-08, 0.251453817)
                elseif _G.SelectBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" then
                    MsBoss = "Cursed Captain [Lv. 1325] [Raid Boss]"
                    NameBoss = "Cursed Captain"
                    CFrameBoss = CFrame.new(916.928589, 181.092773, 33422, -0.999505103, 9.26310495e-09, 0.0314563364, 8.42916226e-09, 1, -2.6643713e-08, -0.0314563364, -2.63653774e-08, -0.999505103)
                elseif _G.SelectBoss == "Darkbeard [Lv. 1000] [Raid Boss]" then
                    MsBoss = "Darkbeard [Lv. 1000] [Raid Boss]"
                    NameBoss = "Darkbeard"
                    CFrameBoss = CFrame.new(3876.00366, 24.6882591, -3820.21777, -0.976951957, 4.97356325e-08, 0.213458836, 4.57335361e-08, 1, -2.36868622e-08, -0.213458836, -1.33787044e-08, -0.976951957)
                elseif _G.SelectBoss == "Order [Lv. 1250] [Raid Boss]" then
                    MsBoss = "Order [Lv. 1250] [Raid Boss]"
                    NameBoss = "Order"
                    CFrameBoss = CFrame.new(-6221.15039, 16.2351036, -5045.23584, -0.380726993, 7.41463495e-08, 0.924687505, 5.85604774e-08, 1, -5.60738549e-08, -0.924687505, 3.28013137e-08, -0.380726993)
                elseif _G.SelectBoss == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
                    MsBoss = "Awakened Ice Admiral [Lv. 1400] [Boss]"
                    NameBoss = "Awakened Ice Admiral"
                    NameQuestBoss = "FrostQuest"
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(5669.33203, 28.2118053, -6481.55908, 0.921275556, -1.25320829e-08, 0.388910472, 4.72230788e-08, 1, -7.96414241e-08, -0.388910472, 9.17372489e-08, 0.921275556)
                    CFrameBoss = CFrame.new(6407.33936, 340.223785, -6892.521, 0.49051559, -5.25310213e-08, -0.871432424, -2.76146022e-08, 1, -7.58250565e-08, 0.871432424, 6.12576301e-08, 0.49051559)
                elseif _G.SelectBoss == "Tide Keeper [Lv. 1475] [Boss]" then
                    MsBoss = "Tide Keeper [Lv. 1475] [Boss]"
                     NameBoss = "Tide Keeper"
                    NameQuestBoss = "ForgottenQuest"             
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-3053.89648, 236.881363, -10148.2324, -0.985987961, -3.58504737e-09, 0.16681771, -3.07832915e-09, 1, 3.29612559e-09, -0.16681771, 2.73641976e-09, -0.985987961)
                    CFrameBoss = CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202)
                -- Thire World
                elseif _G.SelectBoss == "Stone [Lv. 1550] [Boss]" then
                    MsBoss = "Stone [Lv. 1550] [Boss]"
                    NameBoss = "Stone"
                    NameQuestBoss = "PiratePortQuest"             
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-290, 44, 5577)
                    CFrameBoss = CFrame.new(-1085, 40, 6779)
                elseif _G.SelectBoss == "Island Empress [Lv. 1675] [Boss]" then
                    MsBoss = "Island Empress [Lv. 1675] [Boss]"
                     NameBoss = "Island Empress"
                    NameQuestBoss = "AmazonQuest2"             
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(5443, 602, 752)
                    CFrameBoss = CFrame.new(5659, 602, 244)
                elseif _G.SelectBoss == "Kilo Admiral [Lv. 1750] [Boss]" then
                    MsBoss = "Kilo Admiral [Lv. 1750] [Boss]"
                    NameBoss = "Kilo Admiral"
                    NameQuestBoss = "MarineTreeIsland"             
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(2178, 29, -6737)
                    CFrameBoss =CFrame.new(2846, 433, -7100)
                elseif _G.SelectBoss == "Captain Elephant [Lv. 1875] [Boss]" then
                    MsBoss = "Captain Elephant [Lv. 1875] [Boss]"
                    NameBoss = "Captain Elephant"
                    NameQuestBoss = "DeepForestIsland"             
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-13232, 333, -7631)
                    CFrameBoss = CFrame.new(-13221, 325, -8405)
                elseif _G.SelectBoss == "Beautiful Pirate [Lv. 1950] [Boss]" then
                    MsBoss = "Beautiful Pirate [Lv. 1950] [Boss]"
                    NameBoss = "Beautiful Pirate"
                    NameQuestBoss = "DeepForestIsland2"             
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-12686, 391, -9902)
                    CFrameBoss = CFrame.new(5182, 23, -20)
                elseif _G.SelectBoss == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
                    MsBoss = "rip_indra True Form [Lv. 5000] [Raid Boss]"
                    NameBoss = "rip_indra True Form"
                    CFrameBoss = CFrame.new(-5359, 424, -2735)
                elseif _G.SelectBoss == "Longma [Lv. 2000] [Boss]" then
                    MsBoss = "Longma [Lv. 2000] [Boss]"
                    NameBoss = "Longma"
                    CFrameBoss = CFrame.new(-10248.3936, 353.79129, -9306.34473)
                elseif _G.SelectBoss == "Soul Reaper [Lv. 2100] [Raid Boss]" then
                    MsBoss = "Soul Reaper [Lv. 2100] [Raid Boss]"
                    NameBoss = "Soul Reaper"
                    CFrameBoss = CFrame.new(-9515.62109, 315.925537, 6691.12012)
                elseif _G.SelectBoss == "Cake Queen [Lv. 2175] [Boss]" then
                    MsBoss = "Cake Queen [Lv. 2175] [Boss]"
                    NameBoss = "Cake Queen"
                    NameQuestBoss = "IceCreamIslandQuest"             
                    LevelQuestBoss = 3
                    CFrameQuestBoss = CFrame.new(-821.267456, 65.9448776, -10964.3994, 0.814093888, -3.67296735e-08, -0.58073324, 3.30765637e-08, 1, -1.6879099e-08, 0.58073324, -5.46748513e-09, 0.814093888)
                    CFrameBoss = CFrame.new(-715.467102, 381.69104, -11019.8896, 0.955998719, -1.07319993e-08, -0.293370903, 5.00311881e-09, 1, -2.02781667e-08, 0.293370903, 1.7918131e-08, 0.955998719)
                end
            end
        
            function TP(P1)
                local Speed = 10
                local Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
                if Distance < 150 then
                    Speed = 2000
                elseif Distance < 200 then
                    Speed = 1500
                elseif Distance < 300 then
                    Speed = 1000
                elseif Distance < 500 then
                    Speed = 500
                elseif Distance < 1000 then
                    Speed = 300
                elseif Distance >= 1000 then
                    Speed = 300
                end
                Clip = true
                game:GetService("TweenService"):Create(
                    game.Players.LocalPlayer.Character.HumanoidRootPart,
                    TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
                    {CFrame = P1}
                ):Play()
                Clip = false
            end
        
        function TP2(P1)
            local Speed = 10
            local Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
            if Distance < 150 then
                Speed = 200
            elseif Distance < 300 then
                Speed = 225
            elseif Distance < 500 then
                Speed = 200
            elseif Distance < 1000 then
                Speed = 170
            elseif Distance >= 1000 then
                Speed = 200
            end
            game:GetService("TweenService"):Create(
                game.Players.LocalPlayer.Character.HumanoidRootPart,
                TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
                {CFrame = P1}
            ):Play()
        end
        
        function EquipWeapon(ToolSe)
            if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
                local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
                wait(.4)
                game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
            end
        end
        
        spawn(function()
            while game:GetService("RunService").Stepped:wait() do
                character = game.Players.LocalPlayer.Character 
                if Auto_Farm or Ability_Mink_V2 or Saber_Farm or Pole_V1_Hop or Ability_Skypie_V3 or Ability_Mink_V1 or Ability_Human_V3 or Ability_Mink_V3 or Ability_Fish_V3 or Clip or Auto_Farm_Melee or Auto_Farm_Sword or Auto_Farm_Bone or Auto_Farm_Fruit or Mix_Farm or Bartlio_Farm or Saber_Farm or NextIsland or Auto_New_World or Auto_Three_World then
                    pcall(function()
                        for _, v in pairs(character:GetChildren()) do
                            if v:IsA("BasePart") then
                                v.CanCollide = false
                            end
                        end
                    end)
                end
            end
        end)
        
        spawn(function()
            while task.wait() do
                if Auto_Farm or Auto_Farm_Bone or  Ability_Human_V3 or Ability_Fish_V3 or Ability_Mink_V1  or Ability_Mink_V3 or Ability_Skypie_V3 or Saber_Farm or Pole_V1_Hop or Ability_Mink_V2 or Auto_Farm_Sword or Auto_Farm_Melee or Auto_Farm_Fruit or Clip or Mix_Farm or Bartlio_Farm or Saber_Farm or NextIsland or Auto_New_World or Auto_Three_World then
                    if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyVelocity") then 
                        local L_1 = Instance.new("BodyVelocity") 
                        L_1.Name = "BodyGyrozz"
                        L_1.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart 
                        L_1.MaxForce=Vector3.new(100000,100000,100000)
                        L_1.Velocity=Vector3.new(0,0,0) 
                    end
                else
                    if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyGyrozz") then
                        game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyGyrozz"):Destroy()
                    end
                end
            end
        end)
        local library = loadstring(game:HttpGet('https://raw.githubusercontent.com/x7Swiftz/Ui-Switch-HUb/main/README.md'))()
        local HoverPage = library:CreateWindow("Switch Hub ･ Premium™ Max™ Ultimate™ ",Enum.KeyCode.RightControl)
        
        local Main_P = HoverPage:CreateTab("Main")
        local Status_P = HoverPage:CreateTab("Status")
        local Item_P = HoverPage:CreateTab("Item & Quest")
        local Race_P = HoverPage:CreateTab("Race")
        local Island_P = HoverPage:CreateTab("PvP")
        local Raid_P = HoverPage:CreateTab("Raid")
        local Shop_P = HoverPage:CreateTab("Shop")
        local Island_P = HoverPage:CreateTab("Island")
        --local Setting_P = HoverPage:CreateTab("Setting")
        
        local Race_S = Race_P:CreateSector("Main","Left")
        local Race_E = Race_P:CreateSector("Evo Race","Right")
        
        local AutoFarm_Level = Main_P:CreateSector("Farm Level","Left")
        local AutoFarm_Boss = Main_P:CreateSector("Farm Boss","Left")
        local AutoFarm_Mastery = Main_P:CreateSector("Farm Mastery","Left")
        local AutoFarm_Misc = Main_P:CreateSector("Farm Misc","Right")
        local AutoFarm_Item = Main_P:CreateSector("Farm Item","Right")
        local AutoFarm_Lock = Main_P:CreateSector("Farm Lock","Right")
        
        local Status_S = Status_P:CreateSector("Main","Left")
        local Status_I = Status_P:CreateSector("Inventory","Left")
        local Status_K = Status_P:CreateSector("Kill","Right")
        local Status_B = Status_P:CreateSector("Bone","Right")
        local AutoStats_S = Status_P:CreateSector("Auto Stats","Right")
        
        local Melee_S = Item_P:CreateSector("Farm Melee","Right")
        local Sword_S = Item_P:CreateSector("Farm Sword","Right")
        local Gun_S = Item_P:CreateSector("Farm Gun","Right")
        local Accessory_S = Item_P:CreateSector("Farm Accessory","Right")
        local Quest_M = Item_P:CreateSector("Quest Main","Left")
        local Quest_S = Item_P:CreateSector("Quest","Left")
        
        local Raid_S = Raid_P:CreateSector("Main","Left")
        
        local Shop_S = Shop_P:CreateSector("Main","Left")
        local Shop_M = Shop_P:CreateSector("Misc","Left")
        local Shop_F = Shop_P:CreateSector("Fragments","Left")
        local Shop_Fruit = Shop_P:CreateSector("Fruit","Right")
        local Shop_Melee = Shop_P:CreateSector("Melee","Right")
        local Shop_Sword = Shop_P:CreateSector("Sword","Right")
        local Shop_Gun = Shop_P:CreateSector("Gun","Right")
        
        local ISland_S = Island_P:CreateSector("Main","Left")
        local ISland_W = Island_P:CreateSector("World","Left")
        local ISland_I = Island_P:CreateSector("Island","Right")
        
        AutoFarm_Level:AddToggle("AutoFarm",_G.Setting_table.Auto_Farm,function(vu)
            Auto_Farm = vu
            _G.Setting_table.Auto_Farm = vu
            savesetting()
        end)
        spawn(function()
            game:GetService("RunService").Heartbeat:Connect(function()
                pcall(function()
                    local MyLevel = game.Players.LocalPlayer.Data.Level.Value
                    if StatrMagnet then
                        for y,x in pairs(game.Workspace.Enemies:GetChildren()) do
                            if not string.find(x.Name,"Boss") and(x.HumanoidRootPart.Position-_G.PosMon.Position).Magnitude <= 300 then
                                if x.Humanoid:FindFirstChild("Animator") then
                                    x.Humanoid.Animator:Destroy()
                                end
                                x.HumanoidRootPart.CanCollide = false
                                x.HumanoidRootPart.CFrame = _G.PosMon
                                x.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
                            end
                        end
                    end
                end)
            end)
        end)
        AutoFarm_Level:AddToggle("FastAttack",true,function(vu)
            FastAttack = vu
            _G.Setting_table.FastAttack = vu
            savesetting()
        end)
        local Fast = getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))
        local Lop = Fast[2]
        local yedkuy112 = require(game.Players.LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
        
        spawn(function()
            game:GetService("RunService").Heartbeat:Connect(function()
                pcall(function()
                    if FastAttack then
                        if Auto_Farm or Auto_Farm_Melee or Auto_Farm_Sword then
                            yedkuy112.CameraShakeInstance.CameraShakeState.Inactive = 0
                            Lop.activeController.blocking = false
                            Lop.activeController.timeToNextBlock = 0
                            Lop.activeController.attacking = false
                            Lop.activeController.increment = 3
                            Lop.activeController.hitboxMagnitude = 50
                            Lop.activeController.timeToNextAttack = -(math.huge*math.huge) -- 
                            Lop.activeController:attack()
                        else
                            yedkuy112.CameraShakeInstance.CameraShakeState.Inactive = 0
                            Lop.activeController.blocking = false
                            Lop.activeController.timeToNextBlock = 0
                            Lop.activeController.attacking = false
                            Lop.activeController.increment = 3
                            Lop.activeController.hitboxMagnitude = 50
                            Lop.activeController.timeToNextAttack = -(math.huge*math.huge) -- math.huge^math.huge
                        end
                    end
                end)
            end)
        end)
        
        Waspon = {}
        for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
            if v:IsA("Tool") then
                table.insert(Waspon ,v.Name)
            end
        end
        for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
            if v:IsA("Tool") then
                table.insert(Waspon ,v.Name)
            end
        end
        local SelectW = AutoFarm_Level:AddDropdown("Select Weapon",Waspon,"...",false,function(vu)
            _G.Select_Weapon = vu
        end)
        AutoFarm_Level:AddButton("Refresh Weapon",function()
            SelectW:updateText("...")
            _G.Select_Weapon = nil
            for i,v in pairs(Waspon) do
                SelectW:Remove(v)
            end
            for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                if v:IsA("Tool") then
                    SelectW:Remove(v.Name)
                end
            end
            for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
                if v:IsA("Tool") then
                    SelectW:Remove(v.Name)
                end
            end
            for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                if v:IsA("Tool") then
                    SelectW:Add(v.Name)
                end
            end
            for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
                if v:IsA("Tool") then
                    SelectW:Add(v.Name)
                end
            end
        end)
        spawn(function()
            while wait(.1) do
                if not Mix_Farm then
                    pcall(function()
                        if Auto_Farm then
                            if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                                StatrMagnet = false
                                FastAttack = false
                                CheckLevel()
                                if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 1000 then
                                    TP(CFrameQ)
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                end
                            elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                                StatrMagnet = false
                                CheckLevel()
                                if game.Workspace.Enemies:FindFirstChild(Ms) then
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v.Humanoid.Health > 0 and v.Name == Ms and (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                                            if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
                                                StatrMagnet = true
                                                _G.PosMon = v.HumanoidRootPart.CFrame
                                                v.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                                if v.Humanoid:FindFirstChild("Animator") then
                                                    v.Humanoid.Animator:Destroy()
                                                end
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                FastAttack = true
                                                repeat wait(.2)
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(_G.PosMon*CFrame.new(0,30,0))
                                                until v.Humanoid.Health <= 0 or not v.Parent or Auto_Farm == false or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false or Mix_Farm 
                                                StatrMagnet = false
                                                FastAttack = true
                                            else
                                                StatrMagnet = false
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                                            end
                                        end
                                    end
                                elseif not game.Workspace.Enemies:FindFirstChild(Ms) and not game:GetService("ReplicatedStorage"):FindFirstChild(Ms) then
                                    if (CFrameMon.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 5 then
                                        TP(CFrameMon)
                                    end
                                else
                                    TP(CFrameMon)
                                end
                            end
                        end
                    end)
                end
            end
        end)
        
        AutoFarm_Boss:AddToggle("AutoFarm",_G.Setting_table.Auto_Farm_Boss,function(vu)
            Auto_Farm_Boss = vu
            _G.Setting_table.Auto_Farm_Boss = vu
            savesetting()
        end)
        function Text(value)
            game.StarterGui:SetCore("SendNotification", {
                Title = "Yajok Notfication", 
                Text = value,
                Icon = "",
                Duration = 1.5
            })
        end
        spawn(function()
            while wait(.2) do
                pcall(function()
                    if Auto_Farm_Boss then
                        if _G.SelectBoss == nil then
                        else
                            if Mix_Farm == nil or FarmBoss then
                                if game.Workspace.Enemies:FindFirstChild(_G.SelectBoss) or game.ReplicatedStorage:FindFirstChild(_G.SelectBoss) then
                                    Mix_Farm = true
                                    FarmBoss = true
                                    if game.Workspace.Enemies:FindFirstChild(_G.SelectBoss) then
                                        for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                            if v.Name == _G.SelectBoss then
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                repeat wait()
                                                    v.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                until v.Humanoid.Health <= 0 or not v.Parent or Auto_Farm_Boss == nil
                                                
                                                Mix_Farm = nil
                                                FarmBoss = nil
                                            end
                                        end
                                    else
                                        TP2(game.ReplicatedStorage:FindFirstChild(_G.SelectBoss).HumanoidRootPart.CFrame*CFrame.new(0,50,50))
                                    end
                                elseif _G.Hop_Farm_Boss then
                                    wait(5)
                                    if not game.Workspace.Enemies:FindFirstChild(_G.SelectBoss) and not game.ReplicatedStorage:FindFirstChild(_G.SelectBoss) then
                                        _G.Hop_Farm_Boss_Ex = true
                                    end
                                else
                                    Text("บอสยังไม่เกิด ฟังชั่นนี้เปิดพร้อมฟามเวลได้น้าา!")
                                end
                            end
                        end
                    end
                end)
            end
        end)
        AutoFarm_Boss:AddToggle("AutoFarm All Boss",_G.Setting_table.Auto_Farm_Boss_All,function(vu)
            Auto_Farm_Boss_All = vu
            _G.Setting_table.Auto_Farm_Boss_All = vu
            savesetting()
        end)
        
        spawn(function()
            while wait(.2) do
                pcall(function()
                    if Auto_Farm_Boss_All then
                        if Mix_Farm == nil or FarmBossAll then
                            for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
                                if string.find(v.Name,"Boss") then
                                    Mix_Farm = true
                                    FarmBossAll = true
                                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                        if tostring(v2.ToolTip) == "Melee" then
                                            Melee_E = v2.Name
                                        end
                                    end
                                    if _G.Select_Weapon == nil then
                                        _G.Select_Weapon = Melee_E
                                    end
                                    repeat wait()
                                        spawn(function()
                                            if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 60 then
                                                wait(10)
                                                if v.Humanoid.Health == v.Humanoid.MaxHealth then
                                                    v:Destroy()
                                                end
                                            end
                                        end)
                                        EquipWeapon(_G.Select_Weapon)
                                        TP(v.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                        game:GetService'VirtualUser':CaptureController()
                                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                    until v.Humanoid.Health <= 0 or not v.Parent or Auto_Farm_Boss_All == false
                                    Mix_Farm = nil
                                    FarmBossAll = nil
                                elseif _G.Hop_Farm_All_Boss then
                                    repeat wait(1)
                                        wait(5)
                                        OP = true
                                    until string.find(v.Name,"Boss") or OP
                                    OP = nil
                                    if not string.find(v.Name,"Boss") then
                                        _G.Hop_Farm_All_Boss_Ex = true
                                    end
                                end
                            end
                        end
                    end
                end)
            end
        end)
        
        BossP = {}
        local xx = {}
        for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
            if string.find(v.Name,"Boss") then
                table.insert(xx, v.Name)
            end
        end
        table.sort(xx)
        local result = {}
        
        for key,value in ipairs(xx) do
          if value ~=xx[key+1] then
            table.insert(result,value)
          end
        end
        
        for key,value in ipairs(result) do
            table.insert(BossP, value)
        end
        local SelectBoss = AutoFarm_Boss:AddDropdown("Select Boss",BossP,"...",false,function(vu)
            _G.SelectBoss = vu
        end)
        AutoFarm_Boss:AddButton("Refresh Boss",function()
            SelectBoss:updateText("...")
            for i,v in pairs(BossP) do
                SelectBoss:Remove(v)
            end
            local xx = {}
            for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
                if string.find(v.Name,"Boss") then
                    SelectBoss:Remove(v.Name)
                end
            end
            for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
                if string.find(v.Name,"Boss") then
                    table.insert(xx, v.Name)
                end
            end
            table.sort(xx)
            local result = {}
            for key,value in ipairs(xx) do
                if value ~=xx[key+1] then
                    table.insert(result,value)
                end
            end
            for key,value in ipairs(result) do
                SelectBoss:Add(value)
            end
        end)
        
        AutoFarm_Mastery:AddToggle("AutoFarm Devil Fruit",_G.Setting_table.Auto_Farm_Fruit,function(vu)
            Auto_Farm_Fruit = vu
            _G.Setting_table.Auto_Farm_Fruit = vu
            savesetting()
        end)
        spawn(function()
            while wait() do
                pcall(function()
                    if not Mix_Farm then
                        if Auto_Farm_Fruit then
                            CheckLevel()
                            if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                                StatrMagnet = false
                                CheckLevel()
                                if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1200 then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                else
                                    repeat wait(.3)
                                        TP2(CFrameQ)
                                    until (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 400
                                end
                            else
                                if (CFrameMon.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
                                    StatrMagnet = false
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v:FindFirstChild("Humanoid") or v:FindFirstChild("HumanoidRootPart") then
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            if MinHealth == nil then
                                                MinHealth = 15
                                            end
                                            Fruit_E = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                                            if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 500 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1000 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
                                                _G.Mon = v
                                            end
                                            if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 100 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 300 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 500 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1000 then
                                                _G.Mon = v
                                            end
                                            _G.PosMon = _G.Mon.HumanoidRootPart.CFrame
                                            CFrameMon = _G.Mon.HumanoidRootPart.CFrame
                                            StatrMagnet = true
                                            repeat game:GetService("RunService").Stepped:wait()
                                                local vim = game:service("VirtualInputManager")
                                                        local function hold(keyCode, time)
                                                            vim:SendKeyEvent(true, keyCode, false, game)
                                                            task.wait(time)
                                                            vim:SendKeyEvent(false, keyCode, false, game)
                                                        end
                                                        health = _G.Mon.Humanoid.Health
                                                        maxhealth = _G.Mon.Humanoid.MaxHealth
                                                        percent = (health / maxhealth) * 100
                                                        if percent <= MinHealth then
                                                            EquipWeapon(Fruit_E)
                                                            TP(_G.Mon.HumanoidRootPart.CFrame * CFrame.new(0,-10,0))
                                                            game.Workspace.CurrentCamera.CameraSubject = _G.Mon.Humanoid
                                                            wait(0.5)
                                                            if Auto_Skill_Z and _G.Mon.Humanoid.Health > 0 then
                                                                hold(Enum.KeyCode.Z, 0.1)
                                                            end
                                                            if Auto_Skill_X and _G.Mon.Humanoid.Health > 0 then
                                                                hold(Enum.KeyCode.X, 0.1)
                                                            end
                                                            if Auto_Skill_C and _G.Mon.Humanoid.Health > 0 then
                                                                hold(Enum.KeyCode.C, 0.1)
                                                            end
                                                            if Auto_Skill_V and _G.Mon.Humanoid.Health > 0 then
                                                                hold(Enum.KeyCode.V, 0.1)
                                                            end
                                                        elseif percent > MinHealth then
                                                            if percent > MinHealth then
                                                                game.Workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
                                                                EquipWeapon(_G.Select_Weapon)
                                                                TP(_G.Mon.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
                                                                game:GetService'VirtualUser':CaptureController()
                                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                            end
                                                        end
                                            until _G.Mon.Humanoid.Health <= 0 or not _G.Mon.Parent or Auto_Farm_Fruit == false
                                            StatrMagnet = false
                                            game.Workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
                                        else
                                            TP2(CFrameMon)
                                        end
                                    end
                                else
                                    TP2(CFrameMon*CFrame.new(0,35,0))
                                end
                            end
                        end
                    end
                end)
            end
        end)
        AutoFarm_Mastery:AddToggle("Skill Z",_G.Setting_table.Auto_Skill_Z,function(vu)
            Auto_Skill_Z = vu
            _G.Setting_table.Auto_Skill_Z = vu
            savesetting()
        end)
        AutoFarm_Mastery:AddToggle("Skill X",_G.Setting_table.Auto_Skill_X,function(vu)
            Auto_Skill_X = vu
            _G.Setting_table.Auto_Skill_Z = vu
            savesetting()
        end)
        AutoFarm_Mastery:AddToggle("Skill C",_G.Setting_table.Auto_Skill_C,function(vu)
            Auto_Skill_C = vu
            _G.Setting_table.Auto_Skill_C = vu
            savesetting()
        end)
        AutoFarm_Mastery:AddToggle("Skill V",_G.Setting_table.Auto_Skill_V,function(vy)
            Auto_Skill_V = vu
            _G.Setting_table.Auto_Skill_V = vu
            savesetting()
        end)
        AutoFarm_Mastery:AddSlider("Health %",1,15,100,15,function(vu)
            MinHealth = vu
        end)
        AutoFarm_Mastery:AddToggle("AutoFarm Melee",_G.Setting_table.Auto_Farm_Melee,function(vu)
            Auto_Farm_Melee = vu
            _G.Setting_table.Auto_Farm_Melee = vu
            savesetting()
        end)
        spawn(function()
            while wait() do
                pcall(function()
                    if not Mix_Farm then
                        if Auto_Farm_Melee then
                            CheckLevel()
                            if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                                StatrMagnet = false
                                CheckLevel()
                                if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 500 then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                else
                                    repeat wait(.3)
                                        TP2(CFrameQ)
                                    until (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 400
                                end
                            else
                                if (CFrameMon.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
                                    StatrMagnet = false
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v.Humanoid.Health > 0 and v:FindFirstChild("Humanoid") or v.Humanoid.Health > 0 and v:FindFirstChild("HumanoidRootPart") then
                                            if (v.HumanoidRootPart.Position-CFrameMon.Position).Magnitude <= 2000 then
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 100 then
                                                    _G.Mon = v
                                                elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 500 then
                                                    _G.Mon = v
                                                elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1000 then
                                                    _G.Mon = v
                                                elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                                                    _G.Mon = v
                                                elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
                                                    _G.Mon = v
                                                end
                                                _G.PosMon = _G.Mon.HumanoidRootPart.CFrame
                                                CFrameMon = _G.Mon.HumanoidRootPart.CFrame
                                                _G.Mon.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                                StatrMagnet = true
                                                repeat wait(.2)
                                                    EquipWeapon(Melee_E)
                                                    TP(_G.Mon.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                                until _G.Mon.Humanoid.Health <= 0 or not _G.Mon.Parent or Auto_Farm_Melee == false
                                                StatrMagnet = false
                                            end
                                        else
                                            TP2(CFrameMon)
                                        end
                                    end
                                else
                                    TP2(CFrameMon*CFrame.new(0,35,0))
                                end
                            end
                        end
                    end
                end)
            end
        end)
        AutoFarm_Mastery:AddToggle("AutoFarm Sword",_G.Setting_table.Auto_Farm_Sword,function(vu)
            Auto_Farm_Sword = vu
            _G.Setting_table.Auto_Farm_Sword = vu
            savesetting()
        end)
        spawn(function()
            while wait() do
                pcall(function()
                    if not Mix_Farm then
                        if Auto_Farm_Sword then
                            CheckLevel()
                            if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                                StatrMagnet = false
                                CheckLevel()
                                if (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1200 then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuest, QuestLv)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                else
                                    repeat wait(.3)
                                        TP2(CFrameQ)
                                    until (CFrameQ.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 400
                                end
                            else
                                if (CFrameMon.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
                                    StatrMagnet = false
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v:FindFirstChild("Humanoid") or v:FindFirstChild("HumanoidRootPart") then
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Sword" then
                                                    Sword_E = v2.Name
                                                end
                                            end
                                            if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 100 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 500 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1000 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                                                _G.Mon = v
                                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
                                                _G.Mon = v
                                            end
                                            _G.PosMon = _G.Mon.HumanoidRootPart.CFrame
                                            CFrameMon = _G.Mon.HumanoidRootPart.CFrame
                                            _G.Mon.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                            StatrMagnet = true
                                            repeat wait(.2)
                                                EquipWeapon(Sword_E)
                                                TP(_G.Mon.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                            until _G.Mon.Humanoid.Health <= 0 or not _G.Mon.Parent or Auto_Farm_Sword == false
                                            StatrMagnet = false
                                        else
                                            TP2(CFrameMon)
                                        end
                                    end
                                else
                                    TP2(CFrameMon*CFrame.new(0,35,0))
                                end
                            end
                        end
                    end
                end)
            end
        end)
        AutoFarm_Lock:AddDropdown("Select Weapon Lock Mastery",Waspon,"...",false,function(vu)
            _G.WP_Lock = vu
        end)
        AutoFarm_Lock:AddSlider("Lock Mastery 🔒",0,350,600,350,function(vu)
            LockMastery = vu
        end)
        spawn(function()
            while wait(1) do
                pcall(function()
                    if LockMastery > 1 and _G.WP_Lock ~= nil then
                        if game.Players.LocalPlayer.Character:FindFirstChild(_G.WP_Lock) and game.Players.LocalPlayer.Character:FindFirstChild(_G.WP_Lock).Level.Value >= LockMastery or game.Players.LocalPlayer.Backpack:FindFirstChild(_G.WP_Lock) and game.Players.LocalPlayer.Backpack:FindFirstChild(_G.WP_Lock).Level.Value >= LockMastery then
                            TP_Ser = true
                            game.Players.LocalPlayer:Kick("\nฟามเสร็จแล้ว! "..tostring(_G.WP_Lock).." = "..tostring(LockMastery).." มาสเตอรี่\n".."Name : "..tostring(game.Players.LocalPlayer))
                        end
                    end
                end)
            end
        end)
        AutoFarm_Misc:AddToggle("AutoFarm Bone",_G.Setting_table.Auto_Farm_Bone,function(vu)
            Auto_Farm_Bone = vu
            _G.Setting_table.Auto_Farm_Bone = vu
            savesetting()
        end)
        spawn(function()
            while wait() do
                pcall(function()
                    if not Mix_Farm then
                        if Auto_Farm_Bone then
                            Ms = "Reborn Skeleton [Lv. 1975]"
                            if game.Workspace.Enemies:FindFirstChild(Ms) then
                                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                    if v.Name == Ms then
                                        StatrMagnet = false
                                        for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                            if tostring(v2.ToolTip) == "Melee" then
                                                Melee = v2.Name
                                            end
                                        end
                                        if _G.Select_Weapon == nil then
                                            _G.Select_Weapon = Melee_E
                                        end
                                        _G.PosMon = v.HumanoidRootPart.CFrame
                                        CFrameMon = v.HumanoidRootPart.CFrame
                                        StatrMagnet = true
                                        repeat wait()
                                            EquipWeapon(_G.Select_Weapon)
                                            v.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                            TP(v.HumanoidRootPart.CFrame*CFrame.new(0,35,0))
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                        until v.Humanoid.Health <= 0 or not v.Parent or Auto_Farm_Bone == false
                                    end
                                end
                            else
                                TP2(game.ReplicatedStorage:FindFirstChild(Ms).HumanoidRootPart.CFrame*CFrame.new(0,50,0))
                            end
                        end
                    end
                end)
            end
        end)
        local PlaceID = game.PlaceId
        local AllIDs = {}
        local foundAnything = ""
        local actualHour = os.date("!*t").hour
        local Deleted = false
        local File = pcall(function()
            AllIDs = game:GetService('HttpService'):JSONDecode(readfile("NotSameServers.json"))
        end)
        if not File then
            table.insert(AllIDs, actualHour)
            writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
        end
        
        function HopLowerServer()
            game.StarterGui:SetCore("SendNotification", {
                Title = "Hop LowServer", 
                Text = "กำลังหาเซิฟ",
                Icon = "http://www.roblox.com/asset/?id=9370135749",
                Duration = 10
            })
            TP_Ser = true
            local maxplayers, gamelink, goodserver, data_table = math.huge, "https://games.roblox.com/v1/games/" .. game.PlaceId .. "/servers/Public?sortOrder=Asc&limit=100"
            if not _G.FailedServerID then _G.FailedServerID = {} end
            local function serversearch()
                data_table = game:GetService"HttpService":JSONDecode(game:HttpGetAsync(gamelink))
                for _, v in pairs(data_table.data) do
                    pcall(function()
                        if type(v) == "table" and v.id and v.playing and tonumber(maxplayers) > tonumber(v.playing) and not table.find(_G.FailedServerID, v.id) then
                            game.StarterGui:SetCore("SendNotification", {
                                Title = "Hop LowServer", 
                                Text = "Players : "..tostring(v.playing),
                                Icon = "http://www.roblox.com/asset/?id=9370135749",
                                Duration = 2.5
                            })
                           _G.Teleport = true
                            maxplayers = v.playing
                            goodserver = v.id
                        end
                    end)
                end
            end
            function getservers()
                pcall(serversearch)
                for i, v in pairs(data_table) do
                    if i == "nextPageCursor" then
                        if gamelink:find"&cursor=" then
                            local a = gamelink:find"&cursor="
                            local b = gamelink:sub(a)
                            gamelink = gamelink:gsub(b, "")
                        end
                        gamelink = gamelink .. "&cursor=" .. v
                        pcall(getservers)
                    end
                end
            end
            pcall(getservers)
            if goodserver == game.JobId or maxplayers == #game:GetService"Players":GetChildren() - 1 then
            end
            table.insert(_G.FailedServerID, goodserver)
            TP_Ser = true
            game:GetService"TeleportService":TeleportToPlaceInstance(game.PlaceId, goodserver)
        end
        
        function HopServer()
            game.StarterGui:SetCore("SendNotification", {
                Title = "HopServer", 
                Text = "กำลังหาเซิฟ",
                Icon = "http://www.roblox.com/asset/?id=9370135749",
                Duration = 15
            })
            local PlaceID = game.PlaceId
            local AllIDs = {}
            local foundAnything = ""
            local actualHour = os.date("!*t").hour
            local Deleted = false
            function TPReturner()
                local Site;
                if foundAnything == "" then
                    Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
                else
                    Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
                end
                local ID = ""
                if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
                    foundAnything = Site.nextPageCursor
                end
                local num = 0;
                for i,v in pairs(Site.data) do
                    local Possible = true
                    ID = tostring(v.id)
                    game.StarterGui:SetCore("SendNotification", {
                        Title = "HopServer", 
                        Text = "Players : " ..tonumber(v.playing),
                        Icon = "http://www.roblox.com/asset/?id=9370135749",
                        Duration = 1.5
                    })
                    if tonumber(v.maxPlayers) > tonumber(v.playing) then
                        for _,Existing in pairs(AllIDs) do
                            if num ~= 0 then
                                if ID == tostring(Existing) then
                                    Possible = false
                                end
                            else
                                if tonumber(actualHour) ~= tonumber(Existing) then
                                    local delFile = pcall(function()
                                        -- delfile("NotSameServers.json")
                                        AllIDs = {}
                                        table.insert(AllIDs, actualHour)
                                    end)
                                end
                            end
                            num = num + 1
                        end
                        if Possible == true then
                            table.insert(AllIDs, ID)
                            wait()
                            pcall(function()
                                TP_Ser = true
                                -- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
                                wait()
                                game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
                            end)
                            wait(.1)
                        end
                    end
                end
            end
            function Bring()
                while wait(.2) do
                    pcall(function()
                        TPReturner()
                        if foundAnything ~= "" then
                            TPReturner()
                        end
                    end)
                end
            end
            Bring()
        end
        AutoFarm_Misc:AddToggle("AutoFarm Elite Hunter",_G.Setting_table.EliteHunter,function(vu)
            EliteHunter = vu
            _G.Setting_table.EliteHunter = vu
            savesetting()
        end)
        Mp = 0
        if Three_World then
            Mp = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")
        end
        local K_E_H = Status_K:AddLabel("Kill Elite Hunter : "..tostring(Mp))
        spawn(function()
            while wait(.1) do
                pcall(function()
                    if EliteHunter then
                        if Three_World then
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                            wait(25)
                        end
                            if Mix_Farm == nil or EH_Farm then
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
                                    Mix_Farm = true
                                    EH_Farm = true
                                    
                                    wait(1)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Urban [Lv. 1750]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                until v.Humanoid.Health <= 0 or not v.Parent or EliteHunter == false
                                                
                                                K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                Mix_Farm = nil
                                                EH_Farm = nil
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame)
                                    end
                                elseif game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
                                    Mix_Farm = true
                                    EH_Farm = true
                                    
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Diablo [Lv. 1750]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                until v.Humanoid.Health <= 0 or not v.Parent or EliteHunter == false
                                                K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                
                                                Mix_Farm = nil
                                                EH_Farm = nil
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame)
                                    end
                                elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                    Mix_Farm = true
                                    EH_Farm = true
                                    
                                    wait(1)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Deandre [Lv. 1750]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                until v.Humanoid.Health <= 0 or not v.Parent or EliteHunter == false
                                                
                                                K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                
                                                Mix_Farm = nil
                                                EH_Farm = nil
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame)
                                    end
                                elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Urban (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Deandre (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Diablo (0/1)" then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                                    Mix_Farm = nil
                                    EH_Farm = nil
                                elseif _G.Hop_Elite_Hunter then
                                    wait(5)
                                    if not game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                        _G.Hop_Elite_Hunter_Ex = true
                                    end
                                end
                            end
                    end
                end)
            end
        end)
        AutoFarm_Misc:AddButton("Redeem All Code",function()
            function UseCode(Text)
                game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
            end
            UseCode("Sub2Fer999")
            UseCode("Enyu_is_Pro")
            UseCode("Magicbus")
            UseCode("JCWK")
            UseCode("Starcodeheo")
            UseCode("Bluxxy")
            UseCode("THEGREATACE")
            UseCode("SUB2GAMERROBOT_EXP1")
            UseCode("StrawHatMaine")
            UseCode("Sub2OfficialNoobie")
            UseCode("SUB2NOOBMASTER123")
            UseCode("Sub2Daigrock")
            UseCode("Axiore")
            UseCode("TantaiGaming")
            UseCode("STRAWHATMAINE")
        end)
        if _G.Setting_table.Melee == nil then
            _G.Setting_table.Melee = true
        end
        if _G.Setting_table.Defense == nil then
            _G.Setting_table.Defense = true
        end
        AutoStats_S:AddToggle("Melee",_G.Setting_table.Melee,function(vu)
            Melee_A = vu
            _G.Setting_table.Melee = vu
            savesetting()
        end)
        AutoStats_S:AddToggle("Defense",_G.Setting_table.Defense,function(vu)
            Defense_A = vu
            _G.Setting_table.Defense = vu
            savesetting()
        end)
        AutoStats_S:AddToggle("Sword",_G.Setting_table.Sword,function(vu)
            Sword_A = vu
            _G.Setting_table.Sword = vu
            savesetting()
        end)
        AutoStats_S:AddToggle("Fruit",_G.Setting_table.Fruit,function(vu)
            Fruit_A = vu
            _G.Setting_table.Fruit = vu
            savesetting()
        end)
        AutoStats_S:AddToggle("Gun",_G.Setting_table.Gun,function(vu)
            Gun_A = vu
            _G.Setting_table.Gun = vu
            savesetting()
        end)
        if Points == nil then
            Points = 1
        end
        AutoStats_S:AddSlider("Point ",1,3,15,3,function(vu)
            Points = vu
        end)
        spawn(function()
            while wait(.1) do
                if Melee_A then
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Melee", Points)
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.1) do
                if Defense_A then
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Defense", Points)
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.1) do
                if Sword_A then
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Sword", Points)
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.1) do
                if Gun_A then
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Gun", Points)
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.1) do
                if Fruit_A then
                    if game:GetService("Players").LocalPlayer.Data.Points.Value > 0 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Demon Fruit", Points)
                    end
                end
            end
        end)
        
        Melee_S:AddToggle("Auto Superhuman",_G.Setting_table.Superhuman_A,function(vu)
            Superhuman_A = vu
            _G.Setting_table.Superhuman_A = vu
            savesetting()
            if Superhuman_A then
                local args = {
                    [1] = "BuyBlackLeg"
                }
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end
        end)
        if _G.Hop_Superhuman_Ex then
            local args = {
                [1] = "BuyBlackLeg"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end
        spawn(function()
            while wait(.1) do
                if Superhuman_A and not _G.Hop_Superhuman_Ex then
                        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                        local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if game:GetService("Players").LocalPlayer.Data.Beli.Value > 150000 then
                                if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
                                    local args = {
                                        [1] = "BuyBlackLeg"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                end   
                            end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") and game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman").Level.Value < 330 then
                            _G.Select_Weapon = "Superhuman"
                            Auto_Farm_Melee = true
                        elseif _G.Hop_Superhuman and game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") and game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman").Level.Value >= 330 then
                            _G.Hop_Superhuman_Ex = true
                        end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                            _G.Select_Weapon = "Black Leg"
                            Auto_Farm_Melee = true
                        end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                            _G.Select_Weapon = "Electro"
                            Auto_Farm_Melee = true
                        end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 299 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                            _G.Select_Weapon = "Fishman Karate"
                            Auto_Farm_Melee = true
                        end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                            _G.Select_Weapon = "Dragon Claw"
                            Auto_Farm_Melee = true
                        end
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local args = {
                                    [1] = "BuyElectro"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            end
                            if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local args = {
                                    [1] = "BuyElectro"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            end
                            
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local args = {
                                    [1] = "BuyFishmanKarate"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            end
                            if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local args = {
                                    [1] = "BuyFishmanKarate"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            end
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                                if FG >= 1500 then
                                    local args = {
                                        [1] = "BlackbeardReward",
                                        [2] = "DragonClaw",
                                        [3] = "2"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                elseif _G.Hop_Superhuman then
                                    _G.Hop_Superhuman_Ex = true
                                end
                            end
                            if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                                if FG >= 1500 then
                                    local args = {
                                        [1] = "BlackbeardReward",
                                        [2] = "DragonClaw",
                                        [3] = "2"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                elseif _G.Hop_Superhuman then
                                    _G.Hop_Superhuman_Ex = true
                                end
                            end
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                                if Beli >= 300000 then
                                    local args = {
                                        [1] = "BuySuperhuman"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                else
                                    _G.Select_Weapon = "Dragon Claw"
                                    Auto_Farm_Melee = true
                                end
                            end
                            if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                                if Beli >= 300000 then
                                    local args = {
                                        [1] = "BuySuperhuman"
                                    }
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                else
                                    _G.Select_Weapon = "Dragon Claw"
                                    Auto_Farm_Melee = true
                                end
                            end
                end
            end
        end)
        Melee_S:AddToggle("Auto Death Step",_G.Setting_table.Death_Step_A,function(vu)
            Death_Step_A = vu
            _G.Setting_table.Death_Step_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.1) do
                if Death_Step_A and not _G.Hop_Death_Step_Ex then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step").Level.Value < 330 then
                        _G.Select_Weapon = "Death Step"
                        Auto_Farm_Melee = true
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                        _G.Select_Weapon = "Black Leg"
                        Auto_Farm_Melee = true
                    elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and not game.Players.LocalPlayer.Character:FindFirstChild("Death Step") then
                        local args = {
                            [1] = "BuyBlackLeg"
                        }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 400 then
                        local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                        if FG >= 5000 and Beli >= 3000000 then
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") ~= 1 then
                                if New_World then
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
                                    Auto_Farm_Melee = false
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
                                                until v.Humanoid.Health <= 0 or not v.Parent
                                                Auto_Farm_Melee = true
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame)
                                    end
                                end
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 1 then
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
                            elseif _G.Hop_Death_Step then
                                _G.Hop_Death_Step_Ex = true
                            end
                        elseif _G.Hop_Death_Step then
                            _G.Hop_Death_Step_Ex = true
                        end
                    end
                    if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 then
                        local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                        if FG >= 5000 and Beli >= 3000000 then
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") ~= 1 then
                                if New_World then
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
                                    Auto_Farm_Melee = false
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
                                                until v.Humanoid.Health <= 0 or not v.Parent
                                                Auto_Farm_Melee = true
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]").HumanoidRootPart.CFrame)
                                    end
                                end
                            elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep") == 1 then
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
                            elseif _G.Hop_Death_Step then
                                _G.Hop_Death_Step_Ex = true
                            end
                        elseif _G.Hop_Death_Step then
                            _G.Hop_Death_Step_Ex = true
                        end
                    end
                end
            end
        end)
        Melee_S:AddToggle("Auto Sharkman Karate",_G.Setting_table.Sharkman_Karate_A,function(vu)
            Sharkman_Karate_A = vu
            _G.Setting_table.Sharkman_Karate_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.1) do
                if Sharkman_Karate_A and not _G.Hop_Sharkman_Karate_Ex then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate").Level.Value < 330 then
                        _G.Select_Weapon = "Sharkman Karate"
                        Auto_Farm_Melee = true
                    elseif _G.Hop_Sharkman_Karate and game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate").Level.Value >= 330 then
                        _G.Hop_Sharkman_Karate_Ex = true
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                        _G.Select_Weapon = "Fishman Karate"
                        Auto_Farm_Melee = true
                    elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and not game.Players.LocalPlayer.Character:FindFirstChild("Sharkman Karate") then
                        local args = {
                                [1] = "BuyFishmanKarate"
                            }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 400 then
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 0 then
                                if New_World then
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
                                    Auto_Farm_Melee = false
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Tide Keeper [Lv. 1475] [Boss]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
                                                until v.Humanoid.Health <= 0 or not v.Parent
                                                wait(2)
                                                if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then  
                                                    if game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key") then
                                                        EquipWeapon("Water Key")
                                                        wait(0.5)
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
                                                    end
                                                end
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame)
                                    end
                                elseif _G.Hop_Sharkman_Karate then
                                    _G.Hop_Sharkman_Karate_Ex = true
                                end
                            elseif FG >= 5000 and Beli >= 3000000 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 1 then
                                local args = {
                                    [1] = "BuySharkmanKarate",
                                    [2] = true
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                local args = {
                                    [1] = "BuySharkmanKarate"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            elseif _G.Hop_Sharkman_Karate then
                                _G.Hop_Sharkman_Karate_Ex = true
                            end
                        end
                        if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 400 then
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 0 then
                                if New_World then
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
                                    Auto_Farm_Melee = false
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Tide Keeper [Lv. 1475] [Boss]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Tide Keeper [Lv. 1475] [Boss]" then
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,700))
                                                until v.Humanoid.Health <= 0 or not v.Parent
                                                wait(2)
                                                if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then  
                                                    if game.Players.LocalPlayer.Character:FindFirstChild("Water Key") or game.Players.LocalPlayer.Backpack:FindFirstChild("Water Key") then
                                                        EquipWeapon("Water Key")
                                                        wait(0.5)
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
                                                    end
                                                end
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Tide Keeper [Lv. 1475] [Boss]").HumanoidRootPart.CFrame)
                                    end
                                elseif _G.Hop_Sharkman_Karate then
                                    _G.Hop_Sharkman_Karate_Ex = true
                                end
                            elseif FG >= 5000 and Beli >= 3000000 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 1 then
                                local args = {
                                    [1] = "BuySharkmanKarate",
                                    [2] = true
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                                local args = {
                                    [1] = "BuySharkmanKarate"
                                }
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                            elseif _G.Hop_Sharkman_Karate then
                                _G.Hop_Sharkman_Karate_Ex = true
                            end
                        end
                    
                end
            end
        end)
        Melee_S:AddToggle("Auto Electric Claw",_G.Setting_table.Electric_Claw_A,function(vu)
            Electric_Claw_A = vu
            _G.Setting_table.Electric_Claw_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.1) do
                if Electric_Claw_A and not _G.Hop_Electric_Claw_Ex then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw").Level.Value < 330 then
                        _G.Select_Weapon = "Electric Claw"
                        Auto_Farm_Melee = true
                    elseif _G.Hop_Electric_Claw and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw").Level.Value > 330 then
                        _G.Hop_Electric_Claw_Ex = true
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                        _G.Select_Weapon = "Electro"
                        Auto_Farm_Melee = true
                    elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and not game.Players.LocalPlayer.Character:FindFirstChild("Electro") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw") then
                        local args = {
                                [1] = "BuyElectro"
                            }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 and Three_World then
                            local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                            local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if FG >= 5000 and Beli >= 3000000 then
                                if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true) == 4 then
                                    if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start") == nil then
                                        if Three_World then
                                        else
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                            wait(25)
                                        end
                                        Auto_Farm_Melee = false
                                        TP2(CFrame.new(-12548, 337, -7481))
                                    end
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
                                end
                            elseif _G.Hop_Electric_Claw then
                                _G.Hop_Electric_Claw_Ex = true
                            end
                        end
                        if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 and Three_World then
                            local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                            local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if FG >= 5000 and Beli >= 3000000 then
                                if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true) == 4 then
                                    if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start") == nil then
                                        if Three_World then
                                        else
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                            wait(25)
                                        end
                                        Auto_Farm_Melee = false
                                        TP2(CFrame.new(-12548, 337, -7481))
                                    end
                                else
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
                                end
                            elseif _G.Hop_Electric_Claw then
                                _G.Hop_Electric_Claw_Ex = true
                            end
                        end
                    
                end
            end
        end)
    
        Melee_S:AddToggle("Auto Dragon Talon",_G.Setting_table.Dragon_Talon_A,function(vu)
            Dragon_Talon_A = vu
            _G.Setting_table.Dragon_Talon_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.1) do
                if Dragon_Talon_A and not _G.Hop_Dragon_Talon_Ex then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon").Level.Value < 330 then
                        _G.Select_Weapon = "Dragon Talon"
                        Auto_Farm_Melee = true
                        Fire_Shop = false
                    elseif _G.Hop_Dragon_Talon and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon").Level.Value >= 330 then
                        _G.Hop_Dragon_Talon_Ex = true
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                        _G.Select_Weapon = "Dragon Claw"
                        if Three_World then
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                            wait(25)
                        end
                        Auto_Farm_Bone = true
                    elseif not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and not game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and not game.Players.LocalPlayer.Character:FindFirstChild("Dragon Talon") then
                        local args = {
                                [1] = "BlackbeardReward",
                                [2] = "DragonClaw",
                                [3] = "2"
                            }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 400 then
                            local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                            local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if FG >= 5000 and Beli >= 3000000 then
                                Fire_Shop = true
                                if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Bones", "Buy",1,1)
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
                                elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
                                else
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
                                end
                            elseif _G.Hop_Dragon_Talon then
                                _G.Hop_Dragon_Talon_Ex = true
                            end
                        elseif _G.Hop_Dragon_Talon then
                            _G.Hop_Dragon_Talon_Ex = true
                        end
                        if FG >= 5000 and Beli >= 3000000 and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 400 then
                            local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                            local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                            if FG >= 5000 and Beli >= 3000000 then
                                Fire_Shop = true
                                if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Bones", "Buy",1,1)
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
                                elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
                                else
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon",true)
                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
                                end
                            elseif _G.Hop_Dragon_Talon then
                                _G.Hop_Dragon_Talon_Ex = true
                            end
                        elseif _G.Hop_Dragon_Talon then
                            _G.Hop_Dragon_Talon_Ex = true
                        end
                    
                end
            end
        end)
        
        spawn(function()
            while wait(.2) do
                if Fire_Shop then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Fire Essence") or game.Players.LocalPlayer.Character:FindFirstChild("Fire Essence") then
                        local args = {
                            [1] = "BuyDragonTalon",
                            [2] = true
                        }
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                        Fire_Shop = false
                    else
                        local args = {
                            [1] = "Bones",
                            [2] = "Check"
                        }
                        
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                        -- Script generated by SimpleSpy - credits to exx#9394
                        
                        local args = {
                            [1] = "Bones",
                            [2] = "Buy",
                            [3] = 1,
                            [4] = 1
                        }
                        
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                end
            end
        end)
        Sword_S:AddToggle("Auto Saber",_G.Setting_table.Saber_Farm,function(vu)
            Saber_Farm = vu
            _G.Setting_table.Saber_Farm = vu
            savesetting()
        end)
        Sword_S:AddToggle("Auto Pole V1",_G.Setting_table.Pole_V1_Hop,function(vu)
            Pole_V1_Hop = vu
            _G.Setting_table.Pole_V1_Hop = vu
            savesetting()
        end)
        spawn(function()
            while wait() do
                pcall(function()
                    if Pole_V1_Hop then
                        if Old_World then
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
                        end
                        if game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Thunder God [Lv. 575] [Boss]") then
                            if game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
                                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                    if v.Name == "Thunder God [Lv. 575] [Boss]" then
                                        for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                            if tostring(v2.ToolTip) == "Melee" then
                                                Melee_E = v2.Name
                                            end
                                        end
                                        repeat wait(.5)
                                            EquipWeapon(Melee_E)
                                            v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                            TP(v.HumanoidRootPart.CFrame*CFrame.new(0,20,0))
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                        until v.Humanoid.Health <= 0 or not v.Parent or Pole_V1_Hop == false
                                    end
                                end
                            else
                                TP(game:GetService("ReplicatedStorage"):FindFirstChild("Thunder God [Lv. 575] [Boss]").HumanoidRootPart.CFrame)
                            end
                        elseif _G.Hop_PoleV1 then
                            wait(5)
                            if not game:GetService("ReplicatedStorage"):FindFirstChild("Thunder God [Lv. 575] [Boss]") and not game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
                                _G.Hop_PoleV1_Ex = true
                            end
                        end
                    end
                end)
            end
        end)
        spawn(function()
            while wait(.2) do
                local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                if Old_World and Saber_Farm then
                    if Auto_Farm then
                        Auto_Farm = false
                    end
                    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") ~= 0 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                        Auto_Farm = false
                        repeat wait()
                            TP(CFrame.new(-1609.29956, 40.0520697, 162.820404))
                        until (Vector3.new(-1609.29956, 40.0520697, 162.820404)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10
                        wait(3)
                        for i,v in pairs(game:GetService("Workspace").Map.Jungle.QuestPlates:GetChildren()) do
                            if v.Name == "Plate1" then
                                repeat wait()
                                TP2(v.Button.CFrame)
                                until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                wait(1)
                            end
                            if v.Name == "Plate2" then
                                repeat wait()
                                TP2(v.Button.CFrame)
                                until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                wait(1)
                            end
                            if v.Name == "Plate3" then
                                repeat wait()
                                TP2(v.Button.CFrame)
                                until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                wait(1)
                            end
                            if v.Name == "Plate4" then
                                repeat wait()
                                TP2(v.Button.CFrame)
                                until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                wait(1)
                            end
                            if v.Name == "Plate5" then
                                repeat wait()
                                TP2(v.Button.CFrame)
                                until (v.Button.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1
                                wait(1)
                            end
                        end
                        wait(2)
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1609.29956, 12.0520697, 162.820404, -0.993804812, 2.60902091e-08, 0.11113929, 3.47902116e-08, 1, 7.63408607e-08, -0.11113929, 7.97344768e-08, -0.993804812)
                        wait(2)
                        repeat wait()
                            EquipWeapon("Torch")
                            TP(CFrame.new(1113.9502, 4.92147732, 4350.91992, -0.60768199, 3.86533046e-08, 0.794180453, 6.00742425e-08, 1, -2.70375722e-09, -0.794180453, 4.60667628e-08, -0.60768199))
                        until (Vector3.new(1113.9502, 4.92147732, 4350.91992)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1
                        wait(1)
                        --fireclickdetector(game:GetService("Workspace").Map.Desert.Burn.Fire.ClickDetector)
                        wait(1)
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1113.9502, 4.92147732, 4350.91992, -0.60768199, 3.86533046e-08, 0.794180453, 6.00742425e-08, 1, -2.70375722e-09, -0.794180453, 4.60667628e-08, -0.60768199)
                        wait(1)
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1113.9502, 4.92147732, 4350.91992, -0.60768199, 3.86533046e-08, 0.794180453, 6.00742425e-08, 1, -2.70375722e-09, -0.794180453, 4.60667628e-08, -0.60768199)
                        wait(1)
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1114.87708, 4.9214654, 4349.8501, -0.612586915, -9.68697833e-08, 0.790403247, -1.2634203e-07, 1, 2.4638446e-08, -0.790403247, -8.47679615e-08, -0.612586915)
                        wait(10)
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1113.33618, 7.5484705, 4365.56396, -0.618000686, 2.54492516e-08, -0.786177576, -8.16741874e-09, 1, 3.87911392e-08, 0.786177576, 3.03939913e-08, -0.618000686)
                        wait(2)
                        repeat wait()
                            EquipWeapon("Cup")
                            TP(CFrame.new(1397.73975, 37.3480263, -1321.54456, -0.170597032, -4.99889588e-08, 0.985340893, 2.99880867e-08, 1, 5.59246409e-08, -0.985340893, 3.90890662e-08, -0.170597032))
                        until (Vector3.new(1397.73975, 37.3480263, -1321.54456)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2
                        wait(1)
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1397.73975, 37.3480263, -1321.54456, -0.170597032, -4.99889588e-08, 0.985340893, 2.99880867e-08, 1, 5.59246409e-08, -0.985340893, 3.90890662e-08, -0.170597032)
                        wait(3)
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan")
                        wait(1)
                        Mob_Boss = true
                        Saber_Farm = false
                        
                    else
                        Auto_Farm = false
                        Mob_Boss = true
                        Saber_Farm = false
                    end
                elseif not Old_World and Saber_Farm then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
                end
            end
        end)
        
        spawn(function()
            while wait(.2) do
                if Mob_Boss then
                    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 1 then
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Relic") or game.Players.LocalPlayer.Character:FindFirstChild("Relic") then
                            EquipWeapon("Relic")
                            repeat wait()
                                EquipWeapon("Relic")
                                TP2(CFrame.new(-1406.60925, 29.8520069, 4.5805192, 0.882920146, 3.62382622e-08, 0.469523162, -3.61928865e-09, 1, -7.03750587e-08, -0.469523162, 6.04362143e-08, 0.882920146))
                            until (Vector3.new(-1406.60925, 29.8520069, 4.5805192)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2
                            wait(1)
                            Saber_Kill = true
                            Mob_Boss = false
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
                        end
                    elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 0 then
                        if game.Workspace.Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == "Mob Leader [Lv. 120] [Boss]" then
                                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                        if tostring(v2.ToolTip) == "Melee" then
                                            Melee_E = v2.Name
                                        end
                                    end
                                    if _G.Select_Weapon == nil then
                                        _G.Select_Weapon = Melee_E
                                    end
                                    repeat wait()
                                        EquipWeapon(_G.Select_Weapon)
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        TP(v.HumanoidRootPart.CFrame*CFrame.new(0,20,0))
                                        game:GetService'VirtualUser':CaptureController()
                                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                    until not v.Parent or v.Humanoid.Health <= 0 or Mob_Boss == false
                                end
                            end
                        elseif game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
                            TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]").HumanoidRootPart.CFrame)
                        end
                    else
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.2) do
                pcall(function()
                    if Saber_Kill then
                        if game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                            for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                if v.Name == "Saber Expert [Lv. 200] [Boss]" then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                        if tostring(v2.ToolTip) == "Melee" then
                                            Melee_E = v2.Name
                                        end
                                    end
                                    if _G.Select_Weapon == nil then
                                        _G.Select_Weapon = Melee_E
                                    end
                                    repeat wait()
                                        EquipWeapon(_G.Select_Weapon)
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,15))
                                        game:GetService'VirtualUser':CaptureController()
                                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                    until not v.Parent or v.Humanoid.Health <= 0 or Saber_Kill == false
                                end
                            end
                        elseif game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") or game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                            TP(game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]").HumanoidRootPart.CFrame)
                        elseif _G.Hop_Saber then
                            wait(5)
                            if not game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
                                _G.Hop_Saber_Ex = true
                            end
                        else
                            TP2(CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094))
                        end
                    end
                end)
            end
        end)
        Sword_S:AddToggle("Auto Buddy Sword",_G.Setting_table.BuddySword_A,function(vu)
            BuddySword_A = vu
            _G.Setting_table.BuddySword_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.5) do
                if Three_World and BuddySword_A then
                    if Mix_Farm == nil or BuddySword_Farm then
                        if game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
                            Mix_Farm = true
                            BuddySword_Farm = true
                            if game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
                                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                    if v.Name == "Cake Queen [Lv. 2175] [Boss]" then
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                        for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                            if tostring(v2.ToolTip) == "Melee" then
                                                Melee_E = v2.Name
                                            end
                                        end
                                        if _G.Select_Weapon == nil then
                                            _G.Select_Weapon = Melee_E
                                        end
                                        repeat wait()
                                            v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                            EquipWeapon(_G.Select_Weapon)
                                            TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
                                        until v.Humanoid.Health <= 0 or not v.Parent or BuddySword_A == false
                                        
                                        Mix_Farm = nil
                                        BuddySword_Farm = nil
                                    end
                                end
                            else
                                TP(game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]").HumanoidRootPart.CFrame)
                            end
                        elseif _G.Hop_BuddySword then
                            wait(5)
                            if not game:GetService("Workspace").Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
                                _G.Hop_BuddySword_Ex = true
                            end
                        end
                    end
                end
            end
        end)
        Sword_S:AddToggle("Auto Dark Dagger",_G.Setting_table.DarkDagger_A,function(vu)
            DarkDagger_A = vu
            _G.Setting_table.DarkDagger_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.1) do
                pcall(function()
                    if DarkDagger_A then
                        if Three_World then
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                            wait(25)
                        end
                        if Mix_Farm == nil or DarkDagger_Farm then
                            if game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                                
                                Mix_Farm = true
                                DarkDagger_Farm = true
                                if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v.Name == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                            until v.Humanoid.Health <= 0 or not v.Parent or DarkDagger_A == false
                                            
                                            Mix_Farm = nil
                                            DarkDagger_Farm = nil
                                        end
                                    end
                                else
                                    TP2(game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
                                end
                            end
                        end
                    end
                end)
            end
        end)
        Sword_S:AddToggle("Auto Hallow Scryte",_G.Setting_table.Hallow_Scryte_A,function(vu)
            Hallow_Scryte_A = vu
            _G.Setting_table.Hallow_Scryte_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.1) do
                pcall(function()
                    if Hallow_Scryte_A then
                        if Three_World then
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                            wait(25)
                        end
                        if Mix_Farm == nil or Hallow_Scryte_Farm then
                            if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
                                
                                Mix_Farm = true
                                Hallow_Scryte_Farm = true
                                if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
                                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                        if v.Name == "Soul Reaper [Lv. 2100] [Raid Boss]" then
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                EquipWeapon(_G.Select_Weapon)
                                                TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
                                            until v.Humanoid.Health <= 0 or not v.Parent or Hallow_Scryte_A == nil
                                            
                                            Mix_Farm = nil
                                            Hallow_Scryte_Farm = nil
                                        end
                                    end
                                else
                                    TP(game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]").HumanoidRootPart.CFrame)
                                end
                            elseif _G.Hop_HallowScryte then
                                wait(5)
                                if not game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
                                    _G.Hop_HallowScryte_Ex = true
                                end
                            end
                        end
                    end
                end)
            end
        end)
        Sword_S:AddToggle("Auto Spikey Trident",_G.Setting_table.Spikey_Trident_A,function(vu)
            Spikey_Trident_A = vu
            _G.Setting_table.Spikey_Trident_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.5) do
                if Spikey_Trident_A then
                    if Mix_Farm == nil or Spikey_Trident_Farm then
                        if game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
                            
                            Mix_Farm = true
                            Spikey_Trident_Farm = true
                            if game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
                                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                    if v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" then
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                        for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                            if tostring(v2.ToolTip) == "Melee" then
                                                Melee_E = v2.Name
                                            end
                                        end
                                        if _G.Select_Weapon == nil then
                                            _G.Select_Weapon = Melee_E
                                        end
                                        repeat wait()
                                            v.HumanoidRootPart.Size = Vector3.new(5,5,5)
                                            EquipWeapon(_G.Select_Weapon)
                                            TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280,630))
                                        until v.Humanoid.Health <= 0 or not v.Parent or Spikey_Trident_A == false
                                        
                                        Mix_Farm = nil
                                        Spikey_Trident_Farm = true
                                    end
                                end
                            else
                                TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
                            end
                        elseif _G.Hop_SpikeyTrident then
                            wait(5)
                            if not game:GetService("ReplicatedStorage"):FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") and not game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
                                _G.Hop_SpikeyTrident_Ex = true
                            end
                        end
                    end   
                end
            end
        end)
        Sword_S:AddToggle("Auto Yama",_G.Setting_table.Yama_A,function(vu)
            Yama_A = vu
            _G.Setting_table.Yama_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.5) do
                pcall(function()
                    if Yama_A then
                        if Mix_Farm == nil or Yama_Farm then
                            if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress") < 30 then
                                if game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
                                    
                                    Mix_Farm = true
                                    Yama_Farm = true
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Urban [Lv. 1750]" then
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                until v.Humanoid.Health <= 0 or not v.Parent or Yama_A == false
                                                K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                
                                                Mix_Farm = nil
                                                Yama_Farm = nil
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]").HumanoidRootPart.CFrame)
                                    end
                                elseif game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
                                    
                                    Mix_Farm = true
                                    Yama_Farm = true
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Diablo [Lv. 1750]" then
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                until v.Humanoid.Health <= 0 or not v.Parent or Yama_A == false
                                                K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                
                                                Mix_Farm = nil
                                                Yama_Farm = nil
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]").HumanoidRootPart.CFrame)
                                    end
                                elseif game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") or game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                    
                                    Mix_Farm = true
                                    Yama_Farm = true
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                            if v.Name == "Deandre [Lv. 1750]" then
                                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                    if tostring(v2.ToolTip) == "Melee" then
                                                        Melee_E = v2.Name
                                                    end
                                                end
                                                if _G.Select_Weapon == nil then
                                                    _G.Select_Weapon = Melee_E
                                                end
                                                repeat wait()
                                                    EquipWeapon(_G.Select_Weapon)
                                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                    TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                    game:GetService'VirtualUser':CaptureController()
                                                    game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                                until v.Humanoid.Health <= 0 or not v.Parent or Yama_A == false
                                                K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                                
                                                Mix_Farm = nil
                                                Yama_Farm = nil
                                            end
                                        end
                                    else
                                        TP(game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]").HumanoidRootPart.CFrame)
                                    end
                                elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Urban (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Deandre (0/1)" or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Diablo (0/1)" then
                                    HopServer()
                                elseif _G.Hop_Yama then
                                    wait(5)
                                    if not game:GetService("ReplicatedStorage"):FindFirstChild("Urban [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Urban [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Diablo [Lv. 1750]") and not game:GetService("ReplicatedStorage"):FindFirstChild("Deandre [Lv. 1750]") and not game:GetService("Workspace").Enemies:FindFirstChild("Deandre [Lv. 1750]") then
                                        _G.Hop_Yama_Ex = true
                                    end
                                end
                            elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress") >= 30 then
                                
                                Mix_Farm = true
                                Yama_Farm = true
                                if (game.Workspace.Map.Waterfall.SealedKatana.Handle.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 300 then
                                    TP(game.Workspace.Map.Waterfall.SealedKatana.Handle.CFrame)
                                end
                                if game.Workspace.Enemies:FindFirstChild("Ghost [Lv. 1500]") then
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v.Name == "Ghost [Lv. 1500]" then
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                EquipWeapon(_G.Select_Weapon)
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                            until v.Humanoid.Health <= 0 or not v.Parent or Yama_A == false
                                            K_E_H:Set("Kill Elite Hunter : "..tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress")))
                                            
                                            Mix_Farm = nil
                                            Yama_Farm = nil
                                        end
                                    end
                                elseif not game.Workspace.Enemies:FindFirstChild("Ghost [Lv. 1500]") then
                                    fireclickdetector(game.Workspace.Map.Waterfall.SealedKatana.Handle.ClickDetector)
                                end
                            end
                        end
                    end
                end)
            end
        end)
        
        Gun_S:AddToggle("Auto Acidum Rifle",_G.Setting_table.Acidum_Rifle_A,function(vu)
            Acidum_Rifle_A = vu
            _G.Setting_table.Acidum_Rifle_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.2) do
                pcall(function()
                    if Acidum_Rifle_A then
                        if Mix_Farm == nil or Acidum_Rifle_Farm then
                            if game.Workspace.Enemies:FindFirstChild("Core") or game.ReplicatedStorage:FindFirstChild("Core") then
                                if Auto_Farm then
                                    XXXXXXX = true
                                    Acidum_Rifle_Farm = true
                                end
                                Mix_Farm = true
                                Acidum_Rifle_Farm = true
                                if game.Workspace.Enemies:FindFirstChild("Core") then
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v.Name == "Core" then
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                EquipWeapon(_G.Select_Weapon)
                                                TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                            until v.Humanoid.Health <= 0 or not v.Parent or Acidum_Rifle_Farm == false
                                            if XXXXXXX then
                                                XXXXXXX = nil
                                                Auto_Farm = true
                                            end
                                            Mix_Farm = nil
                                            Acidum_Rifle_Farm = nil
                                        end
                                    end
                                else
                                    TP(CFrame.new(402.404296875, 182.53373718262, -414.73394775391))
                                end
                            end
                        end
                    end
                end)
            end
        end)
        Accessory_S:AddToggle("Auto Swan Glass",_G.Setting_table.Swan_Glass_A,function(vu)
            Swan_Glass_A = vu
            _G.Setting_table.Swan_Glass_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.2) do
                pcall(function()
                    if Swan_Glass_A then
                        if Mix_Farm == nil or Swan_Glass_Farm then
                            if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
                                
                                Mix_Farm = true
                                Swan_Glass_Farm = true
                                if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
                                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                        if v.Name == "Don Swan [Lv. 1000] [Boss]" then
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                EquipWeapon(_G.Select_Weapon)
                                                TP(v.HumanoidRootPart.CFrame * CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                            until v.Humanoid.Health <= 0 or not v.Parent or Swan_Glass_A == false
                                            
                                            Mix_Farm = nil
                                            Swan_Glass_Farm = nil
                                        end
                                    end
                                else
                                    TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
                                end
                            end
                        end
                    end
                end)
            end
        end)
        Accessory_S:AddToggle("Auto Valkyrie Helmet",_G.Setting_table.Valkyrie_Helmet_A,function(vu)
            Valkyrie_Helmet_A = vu
            _G.Setting_table.Valkyrie_Helmet_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.1) do
                pcall(function()
                    if Valkyrie_Helmet_A then
                        if Three_World then
                        else
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                            wait(25)
                        end
                        if Mix_Farm == nil or Valkyrie_Helmet_Farm then
                            if game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                                
                                Mix_Farm = true
                                Valkyrie_Helmet_Farm = true
                                if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                                    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                                        if v.Name == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,600))
                                            until v.Humanoid.Health <= 0 or not v.Parent or DarkDagger_A == false
                                            
                                            Mix_Farm = nil
                                            Valkyrie_Helmet_Farm = nil
                                        end
                                    end
                                else
                                    TP2(game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]").HumanoidRootPart.CFrame*CFrame.new(0,50,0))
                                end
                            elseif _G.Hop_DarkDagger then
                                wait(5)
                                if not game:GetService("ReplicatedStorage"):FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") and not game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
                                    _G.Hop_DarkDagger_Ex = true    
                                end
                            end
                        end
                    end
                end)
            end
        end)
        
        Quest_M:AddToggle("Auto New World",_G.Setting_table.Auto_New_A,function(vu)
            Auto_New_A = vu
            _G.Setting_table.Auto_New_A = vu
            savesetting()
        end)
        spawn(function()
            while wait(.2) do
                if Auto_New_A then
                    if Mix_Farm == nil or Auto_New_Farm then
                        local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                        local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                        local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                        if Lv >= 700 then
                            
                            Mix_Farm = true
                            Auto_New_Farm = true
                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective") == 1 then
                            else
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective")
                                wait(2)
                                EquipWeapon("Key")
                            end
                            repeat wait()
                                TP2(CFrame.new(1347.32947, 37.349369, -1325.44922, 0.538348913, 8.57539106e-08, 0.842722058, 8.61935634e-10, 1, -1.0230886e-07, -0.842722058, 5.58042359e-08, 0.538348913))
                            until (Vector3.new(1347.32947, 37.349369, -1325.44922)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1 or Auto_New_A == false
                            wait(2)
                            for i,v in pairs(game.workspace.Enemies:GetChildren()) do
                                if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                        if tostring(v2.ToolTip) == "Melee" then
                                            Melee_E = v2.Name
                                        end
                                    end
                                    if _G.Select_Weapon == nil then
                                        _G.Select_Weapon = Melee_E
                                    end
                                    repeat wait()
                                        EquipWeapon(_G.Select_Weapon)
                                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                        TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,15))
                                        game:GetService'VirtualUser':CaptureController()
                                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                    until v.Humanoid.Health <= 0 or not v.Parent or Auto_New_A == false
                                    wait(2)
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                    wait(25)
                                end
                            end
                        end
                    end
                end
            end
        end)
        Quest_M:AddToggle("Auto Three World",_G.Setting_table.Auto_Three_World,function(vu)
            Auto_Three_World = vu
            _G.Setting_table.Auto_Three_World = vu
            savesetting()
        end)
        spawn(function()
            while wait(.2) do
                pcall(function()
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    if Auto_Three_World and Lv >= 1500 and New_World then
                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 1 then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                            wait(15)
                        elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 0 then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check")
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Begin")
                            wait(5)
                            if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then
                                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                    if v.Name == "rip_indra [Lv. 1500] [Boss]" then
                                        for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                            if tostring(v2.ToolTip) == "Melee" then
                                                Melee_E = v2.Name
                                            end
                                        end
                                        if _G.Select_Weapon == nil then
                                            _G.Select_Weapon = Melee_E
                                        end
                                        repeat wait()
                                            if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 1 then
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                                wait(20)
                                            end
                                            v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                            TP(v.HumanoidRootPart.CFrame*CFrame.new(0,20,0))
                                            EquipWeapon(_G.Select_Weapon)
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                            game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                                        until v.Humanoid.Health <= 0 or not v.Parent or Auto_Three_World == false
                                    end
                                end
                            end
                        end
                    end
                end)
            end
        end)
        
        Quest_S:AddToggle("Auto Bartilo",_G.Setting_table.Bartlio_Farm,function(vu)
            Bartlio_Farm = vu
            _G.Setting_table.Bartlio_Farm = vu
            savesetting()
        end)
        spawn(function()
            while wait(.2) do
                if Bartlio_Farm and New_World then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    local Beli = game:GetService("Players").LocalPlayer.Data.Beli.Value
                    local FG = game:GetService("Players").LocalPlayer.Data.Fragments.Value
                    if Lv >= 900 and _G.Setting_table.Bartlio == nil then
                        Auto_Farm = false
                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
                            if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                                if game.workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
                                    for i,v in pairs(game.workspace.Enemies:GetChildren()) do
                                        if v.Name == "Swan Pirate [Lv. 775]" then
                                            CFrameMon = v.HumanoidRootPart.CFrame
                                            _G.PosMon = v.HumanoidRootPart.CFrame
                                            StatrMagnet = true
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                                if tostring(v2.ToolTip) == "Melee" then
                                                    Melee_E = v2.Name
                                                end
                                            end
                                            if _G.Select_Weapon == nil then
                                                _G.Select_Weapon = Melee_E
                                            end
                                            repeat wait()
                                                EquipWeapon(_G.Select_Weapon)
                                                v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                                TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                                game:GetService'VirtualUser':CaptureController()
                                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                            until v.Humanoid.Health <= 0 or not v.Parent or Bartlio_Farm ==false
                                            StatrMagnet = false
                                        end
                                    end
                                elseif game:GetService("ReplicatedStorage"):FindFirstChild("Swan Pirate [Lv. 775]") then
                                    TP2(game:GetService("ReplicatedStorage"):FindFirstChild("Swan Pirate [Lv. 775]").HumanoidRootPart.CFrame*CFrame.new(0,20,0))
                                end
                            else
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest","BartiloQuest",1)
                            end
                        elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
                            _G.SelectBoss = "Jeremy [Lv. 850] [Boss]"
                            CheckQuestBoss()
                            if game.workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
                                for i,v in pairs(game.workspace.Enemies:GetChildren()) do
                                    if v.Name == "Jeremy [Lv. 850] [Boss]" then
                                        for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                            if tostring(v2.ToolTip) == "Melee" then
                                                Melee_E = v2.Name
                                            end
                                        end
                                        if _G.Select_Weapon == nil then
                                            _G.Select_Weapon = Melee_E
                                        end
                                        repeat wait()
                                            EquipWeapon(_G.Select_Weapon)
                                            v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                            TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280,900))
                                        until v.Humanoid.Health <= 0 or not v.Parent or Bartlio_Farm == false
                                    end
                                end
                            else
                                TP(CFrameBoss)
                            end
                        elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
                            repeat wait()
                                TP2(CFrame.new(-1836, 11, 1714))
                            until (Vector3.new(-1836, 11, 1714)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 2
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1836, 11, 1714)
                                wait(1)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1850.49329, 13.1789551, 1750.89685)
                                wait(1)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.87305, 19.3777466, 1712.01807)
                                wait(1)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1803.94324, 16.5789185, 1750.89685)
                                wait(1)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.55835, 16.8604317, 1724.79541)
                                wait(1)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1869.54224, 15.987854, 1681.00659)
                                wait(1)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1800.0979, 16.4978027, 1684.52368)
                                wait(1)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1819.26343, 14.795166, 1717.90625)
                                wait(1)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1813.51843, 14.8604736, 1724.79541)
                        end
                    end
                end
            end
        end)
        
        Quest_S:AddToggle("Auto Open Don Swan",_G.Setting_table.Open_Don_Swan,function(vu)
            Open_Don_Swan = vu
            _G.Setting_table.Open_Don_Swan = vu
            savesetting()
        end)
        spawn(function()
            while wait() do
                if Open_Don_Swan then
                    local Lv = game:GetService("Players").LocalPlayer.Data.Level.Value
                    if Lv >= 1100 then
                        pcall(function()
                            local Fruit_List = {
                                "Quake-Quake",
                                "Quake Fruit",
                                "Human-Human: Buddha",
                                "Human-Human: Buddha Fruit",
                                "String-String",
                                "String Fruit",
                                "Rumble-Rumble",
                                "Rumble Fruit",
                                "Paw Fruit",
                                "Paw-Paw",
                                "Gravity Fruit",
                                "Gravity-Gravity",
                                "Dough Fruit",
                                "Dough-Dough",
                                "Shadow Fruit",
                                "Shadow-Shadow",
                                "Shadow Fruit",
                                "Venom-Venom",
                                "Venom Fruit",
                                "Control Fruit",
                                "Control-Control",
                                "Dragon Fruit",
                                "Dragon-Dragon"
                            }
                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                                if v2:IsA("Tool") then
                                    if v2.Name == Fruit_List[2] or v2.Name == Fruit_List[4] or v2.Name == Fruit_List[6] or v2.Name == Fruit_List[8] or v2.Name == Fruit_List[9] or v2.Name == Fruit_List[11] or v2.Name == Fruit_List[13] or v2.Name == Fruit_List[15] or v2.Name == Fruit_List[19] or v2.Name == Fruit_List[20] or v2.Name == Fruit_List[22] then
                                        Auto_Farm = false
                                        EquipWeapon(v2.Name)
                                        wait(1)
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
                                        wait(2)
                                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
                                            game.Players.LocalPlayer:Kick("\nเปิดประตูโดฟาสำเร็จ")
                                        end
                                    end
                                end
                            end
                            for i2,v2 in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
                                if v2:IsA("Tool") then
                                    if v2.Name == Fruit_List[2] or v2.Name == Fruit_List[4] or v2.Name == Fruit_List[6] or v2.Name == Fruit_List[8] or v2.Name == Fruit_List[9] or v2.Name == Fruit_List[11] or v2.Name == Fruit_List[13] or v2.Name == Fruit_List[15] or v2.Name == Fruit_List[19] or v2.Name == Fruit_List[20] or v2.Name == Fruit_List[22] then
                                        Auto_Farm = false
                                        EquipWeapon(v2.Name)
                                        wait(1)
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
                                        wait(2)
                                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
                                            game.Players.LocalPlayer:Kick("\nเปิดประตูโดฟาสำเร็จ")
                                        end
                                    end
                                end
                            end
                            game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Visible = true
                            local Value_Fruit = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                            --if Value_Fruit == _G.Select_Fruit[1] or Value_Fruit == _G.Select_Fruit[2] or Value_Fruit == _G.Select_Fruit[3] or Value_Fruit == _G.Select_Fruit[4] or Value_Fruit == _G.Select_Fruit[5] or not CH:FindFirstChild(_G.Fruit_Name[1]) and not CH:FindFirstChild(_G.Fruit_Name[2]) and not CH:FindFirstChild(_G.Fruit_Name[3]) and not CH:FindFirstChild(_G.Fruit_Name[4]) and not CH:FindFirstChild(_G.Fruit_Name[5]) and not BP:FindFirstChild(_G.Fruit_Name[1]) and not BP:FindFirstChild(_G.Fruit_Name[2]) and not BP:FindFirstChild(_G.Fruit_Name[3]) and not BP:FindFirstChild(_G.Fruit_Name[4]) and not BP:FindFirstChild(_G.Fruit_Name[5]) then
                                for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Container.Stored.ScrollingFrame.Frame:GetChildren()) do
                                    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") ~= 0 then
                                        if v.Name == Fruit_List[1] or v.Name == Fruit_List[3] or v.Name == Fruit_List[5] or v.Name == Fruit_List[7] or v.Name == Fruit_List[10] or v.Name == Fruit_List[12] or v.Name == Fruit_List[14] or v.Name == Fruit_List[16] or v.Name == Fruit_List[18] or v.Name == Fruit_List[21] or v.Name == Fruit_List[23] then
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit",v.Name)
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                                                if v2:IsA("Tool") then
                                                    if v2.Name == Fruit_List[2] or v2.Name == Fruit_List[4] or v2.Name == Fruit_List[6] or v2.Name == Fruit_List[8] or v2.Name == Fruit_List[9] or v2.Name == Fruit_List[11] or v2.Name == Fruit_List[13] or v2.Name == Fruit_List[15] or v2.Name == Fruit_List[19] or v2.Name == Fruit_List[20] or v2.Name == Fruit_List[22] then
                                                        Auto_Farm = false
                                                        EquipWeapon(v2.Name)
                                                        wait(1)
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
                                                        wait(2)
                                                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
                                                            game.Players.LocalPlayer:Kick("\nเปิดประตูโดฟาสำเร็จ")
                                                        end
                                                    end
                                                end
                                            end
                                            for i2,v2 in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
                                                if v2:IsA("Tool") then
                                                    if v2.Name == Fruit_List[2] or v2.Name == Fruit_List[4] or v2.Name == Fruit_List[6] or v2.Name == Fruit_List[8] or v2.Name == Fruit_List[9] or v2.Name == Fruit_List[11] or v2.Name == Fruit_List[13] or v2.Name == Fruit_List[15] or v2.Name == Fruit_List[19] or v2.Name == Fruit_List[20] or v2.Name == Fruit_List[22] then
                                                        Auto_Farm = false
                                                        EquipWeapon(v2.Name)
                                                        wait(1)
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
                                                        wait(2)
                                                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
                                                            game.Players.LocalPlayer:Kick("\nเปิดประตูโดฟาสำเร็จ")
                                                        end
                                                    end
                                                end
                                            end
                                        end
                                    end
                                end
                            --end
                        end)
                    end
                end
            end
        end)
        Raid_S:AddToggle("Auto Raid",_G.Setting_table.AutoRaid,function(vu)
            AutoRaid = vu
            _G.Setting_table.AutoRaid = vu
            savesetting()
        end)
        spawn(function()
            while wait(.2) do
                if Kill_Aura then
                    for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
                        if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                            pcall(function()
                                repeat wait(.1)
                                    sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                                    v.Humanoid.Health = 0
                                    v.HumanoidRootPart.CanCollide = false
                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                    v.HumanoidRootPart.Transparency = 0.5
                                until Kill_Aura == false or not v.Parent or v.Humanoid.Health <= 0
                            end)
                        end
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.2) do
                if AutoRaid then
                    wait(2)
                    if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") then
                        if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                            if New_World then
                                fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
                                repeat wait()
                                    wait(1)
                                until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
                            elseif Three_World then
                                fireclickdetector(game:GetService("Workspace").Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
                                repeat wait()
                                    wait(1)
                                until game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true
                            end
                        end
                    elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") and game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false and _G.Hop_Raid then
                        wait(15)
                        if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                            if _G.Hop_Raid then
                                if not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Special Microchip") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Special Microchip") and game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false and _G.Hop_Raid then
                                    _G.Hop_Raid_Ex = true
                                end
                            end
                        end
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.2) do
                if AutoRaid then
                    if _G.SelectMap == nil then
                    else
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", _G.SelectMap)
                    end
                end
            end
        end)
        spawn(function()
            while wait(.1) do
                if AutoRaid then
                    if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == false then
                        TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.1) do
                if NextIsland then
                    wait(3)
                    pcall(function()
                        if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                            for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                if v.Name == "Island 5" then
                                    TP2(v.CFrame*CFrame.new(0,70,0))
                                    --wait(10)
                                end
                            end
                        elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                            for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                if v.Name == "Island 4" then
                                    TP2(v.CFrame*CFrame.new(0,70,0))
                                    --wait(10)
                                end
                            end
                        elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                            for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                if v.Name == "Island 3" then
                                    TP2(v.CFrame*CFrame.new(0,70,0))
                                    --wait(10)
                                end
                            end
                        elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                            for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                if v.Name == "Island 2" then
                                    TP2(v.CFrame*CFrame.new(0,70,0))
                                    --wait(10)
                                end
                            end
                        elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") and (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2500 then
                            for i,v in pairs(game:GetService("Workspace")["_WorldOrigin"].Locations:GetChildren()) do
                                if v.Name == "Island 1" then
                                    TP2(v.CFrame*CFrame.new(0,70,0))
                                    --wait(10)
                                end
                            end
                        end
                    end)
                end
            end
        end)
        
        
        spawn(function()
            pcall(function()
                while wait(1) do
                    if Awaken then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Check")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Awaken")
                    end
                end
            end)
        end)
        Raid_S:AddToggle("Kill Aura",_G.Setting_table.Kill_Aura,function(vu)
            Kill_Aura = vu
            _G.Setting_table.Kill_Aura = vu
            savesetting()
        end)
        Raid_S:AddToggle("Next Island",_G.Setting_table.NextIsland,function(vu)
            NextIsland = vu
            _G.Setting_table.NextIsland = vu
            savesetting()
        end)
        Raid_S:AddToggle("Auto Awaken",_G.Setting_table.Awaken,function(vu)
            Awaken = vu
            _G.Setting_table.Awaken = vu
            savesetting()
        end)
        Map = {
            "Dark",
            "Sand",
            "Magma",
            "Rumble",
            "Flame",
            "Ice",
            "Light",
            "Quake",
            "Human-Human: Buddha",
            "Flame"
        }
        Raid_S:AddDropdown("Select Dungeon",Map,"...",false,function(vu)
            _G.SelectMap = vu
        end)
        Raid_S:AddButton("Buy Chip",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaidsNpc", "Select", _G.SelectMap)    
        end)
        
        ISland_S:AddButton("Hop Server",function()
            HopServer()
        end)
        ISland_S:AddButton("Hop LowerServer",function()
            HopLowerServer()
        end)
        ISland_S:AddButton("Re join",function()
            game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
        end)
        
        Shop_S:AddButton("Buy SkyJump",function()
            local args = {
                [1] = "BuyHaki",
                [2] = "Geppo"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        Shop_S:AddButton("Buy Soru",function()
            local args = {
                [1] = "BuyHaki",
                [2] = "Soru"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        Shop_S:AddButton("Buy Haki",function()
            local args = {
                [1] = "BuyHaki",
                [2] = "Buso"
            }
        
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))    
        end)
        Shop_S:AddButton("Buy KenHaki",function()
            local args = {
                [1] = "KenTalk",
                [2] = "Buy"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        Shop_Fruit:AddToggle("Auto Buy Random Fruit",_G.Setting_table.Auto_Buy_Random_Fruit,function(vu)
            Auto_Buy_Random_Fruit = vu
            _G.Setting_table.Auto_Buy_Random_Fruit = vu
            savesetting()
        end)
        spawn(function()
            while wait(.2) do
                if Auto_Buy_Random_Fruit then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
                    wait(20)
                end
            end
        end)
        
        spawn(function()
            while wait(30) do
                if Sniper_Fruit then
                    for s,f in pairs(_G.Select_Fruit) do
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PurchaseRawFruit",f)
                    end
                end
            end
        end)
        Shop_Fruit:AddToggle("Fruit Inventory",_G.Setting_table.Inventory_Fruit,function(vu)
            Inventory_Fruit = vu
            _G.Setting_table.Inventory_Fruit = vu
            savesetting()
        end)
        if _G.Fruit_Inventory then
            Inventory_Fruit = true
        end
        if _G.SelectFruit == nil then
            _G.SelectFruit = "Dark-Dark","Bird-Bird: Phoenix","Dragon-Dragon","Human-Human: Buddha","",""
        end
        
        spawn(function()
            while wait() do
                if _G.Eat_Fruit then
                    local Value_Fruit = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                    if Value_Fruit == _G.SelectFruit[1] or Value_Fruit == _G.SelectFruit[2] or Value_Fruit == _G.SelectFruit[3] or Value_Fruit == _G.SelectFruit[4] or Value_Fruit == _G.SelectFruit[5] or Value_Fruit == _G.SelectFruit[6] or Value_Fruit == _G.SelectFruit[7] then
                    else
                        _G.Fruit_Name = {}
                        for i,v in pairs(_G.SelectFruit) do
                            if v == "Dark-Dark" then
                                table.insert(_G.Fruit_Name,"Dark Fruit")
                            end
                            if v == "Sand-Sand" then
                                table.insert(_G.Fruit_Name,"Sand Fruit")
                            end
                            if v == "Magma-Magma" then
                                table.insert(_G.Fruit_Name,"Magma Fruit")
                            end
                            if v == "Door-Door" then
                                table.insert(_G.Fruit_Name,"Door Fruit")
                            end
                            if v == "Shadow-Shadow" then
                                table.insert(_G.Fruit_Name,"Shadow Fruit")
                            end
                            if v == "Venom-Venom" then
                                table.insert(_G.Fruit_Name,"Venom Fruit")
                            end
                            if v == "Rumble-Rumble" then
                                table.insert(_G.Fruit_Name,"Rumble Fruit")
                            end
                            if v == "Bird-Bird: Phoenix" then
                                table.insert(_G.Fruit_Name,"Bird: Phoenix Fruit")
                            end
                            if v == "String-String" then
                                table.insert(_G.Fruit_Name,"String Fruit")
                            end
                            if v == "Human-Human: Buddha" then
                                table.insert(_G.Fruit_Name,"Human-Human: Buddha Fruit")
                            end
                            if v == "Dragon-Dragon" then
                                table.insert(_G.Fruit_Name,"Dragon Fruit")
                            end
                            if v == "Light-Light" then
                                table.insert(_G.Fruit_Name,"Light Fruit")
                            end
                            if v == "Quake-Quake" then
                                table.insert(_G.Fruit_Name,"Quake Fruit")
                            end
                            if v == "Soul-Soul" then
                                table.insert(_G.Fruit_Name,"Soul Fruit")
                            end
                            if v == "Ice-Ice" then
                                table.insert(_G.Fruit_Name,"Ice Fruit")
                            end
                        end
                        for y,x in pairs(_G.Fruit_Name) do
                            for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                                if v.Name == x then
                                    Clip = true
                                    EquipWeapon(v.Name)
                                    wait(0.5)
                                    game:GetService("Players").LocalPlayer.Character:FindFirstChild(v.Name).EatRemote:InvokeServer()
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                                    wait(2)
                                    Clip = false
                                end
                            end
                            for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
                                if v.Name == x then
                                    Clip = true
                                    EquipWeapon(v.Name)
                                    wait(0.5)
                                    game:GetService("Players").LocalPlayer.Character:FindFirstChild(v.Name).EatRemote:InvokeServer()
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                                    wait(2)
                                    Clip = false
                                end
                            end
                        end
                    end
                end
            end
        end)
        
        spawn(function()
            while wait(.3) do
                if Inventory_Fruit then
                    if _G.Eat_Fruit then
                        local Value_Fruit = game:GetService("Players").LocalPlayer.Data.DevilFruit.Value
                        if Value_Fruit == _G.SelectFruit[1] or Value_Fruit == _G.SelectFruit[2] or Value_Fruit == _G.SelectFruit[3] or Value_Fruit == _G.SelectFruit[4] or Value_Fruit == _G.SelectFruit[5] or Value_Fruit == _G.SelectFruit[6] or Value_Fruit == _G.SelectFruit[7] then
                        else
                            _G.Fruit_Name = {}
                            for i,v in pairs(_G.SelectFruit) do
                                if v == "Dark-Dark" then
                                    table.insert(_G.Fruit_Name,"Dark Fruit")
                                end
                                if v == "Sand-Sand" then
                                    table.insert(_G.Fruit_Name,"Sand Fruit")
                                end
                                if v == "Magma-Magma" then
                                    table.insert(_G.Fruit_Name,"Magma Fruit")
                                end
                                if v == "Door-Door" then
                                    table.insert(_G.Fruit_Name,"Door Fruit")
                                end
                                if v == "Shadow-Shadow" then
                                    table.insert(_G.Fruit_Name,"Shadow Fruit")
                                end
                                if v == "Venom-Venom" then
                                    table.insert(_G.Fruit_Name,"Venom Fruit")
                                end
                                if v == "Rumble-Rumble" then
                                    table.insert(_G.Fruit_Name,"Rumble Fruit")
                                end
                                if v == "Bird-Bird: Phoenix" then
                                    table.insert(_G.Fruit_Name,"Bird: Phoenix Fruit")
                                end
                                if v == "String-String" then
                                    table.insert(_G.Fruit_Name,"String Fruit")
                                end
                                if v == "Human-Human: Buddha" then
                                    table.insert(_G.Fruit_Name,"Human-Human: Buddha Fruit")
                                end
                                if v == "Dragon-Dragon" then
                                    table.insert(_G.Fruit_Name,"Dragon Fruit")
                                end
                                if v == "Light-Light" then
                                    table.insert(_G.Fruit_Name,"Light Fruit")
                                end
                                if v == "Quake-Quake" then
                                    table.insert(_G.Fruit_Name,"Quake Fruit")
                                end
                                if v == "Soul-Soul" then
                                    table.insert(_G.Fruit_Name,"Soul Fruit")
                                end
                                if v == "Ice-Ice" then
                                    table.insert(_G.Fruit_Name,"Ice Fruit")
                                end
                            end
                            for y,x in pairs(_G.Fruit_Name) do
                                for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
                                    if v.Name == x then
                                        Clip = true
                                        EquipWeapon(v.Name)
                                        wait(0.5)
                                        game:GetService("Players").LocalPlayer.Character:FindFirstChild(v.Name).EatRemote:InvokeServer()
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                                        wait(2)
                                        Clip = false
                                    end
                                end
                                for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
                                    if v.Name == x then
                                        Clip = true
                                        EquipWeapon(v.Name)
                                        wait(0.5)
                                        game:GetService("Players").LocalPlayer.Character:FindFirstChild(v.Name).EatRemote:InvokeServer()
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                                        wait(2)
                                        Clip = false
                                    end
                                end
                            end
                        end
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bomb Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bomb Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bomb-Bomb")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spike Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spike Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spike-Spike")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Chop Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Chop Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Chop-Chop")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spring Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spring Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spring-Spring")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Kilo Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Kilo Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Kilo-Kilo")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Smoke Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Smoke Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Smoke-Smoke")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Spin Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Spin Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Spin-Spin")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Flame-Flame")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Falcon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Falcon Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Falcon")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Ice-Ice")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Sand-Sand")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dark-Dark")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Revive Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Revive Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Revive-Revive")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Diamond Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Diamond Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Diamond-Diamond")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Light-Light")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Love Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Love Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Love-Love")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rubber Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rubber Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rubber-Rubber")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Barrier Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Barrier Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Barrier-Barrier")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Magma-Magma")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Door Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Door Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Door-Door")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Quake-Quake")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Human-Human: Buddha")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("String Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","String-String")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Bird-Bird: Phoenix")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Rumble-Rumble")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Paw Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Paw Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Paw-Paw")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Gravity Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Gravity Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Gravity-Gravity")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dough Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dough Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dough-Dough")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Shadow Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Shadow Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Shadow-Shadow")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Venom Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Venom Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Venom-Venom")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Control Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Control Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Control-Control")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Dragon-Dragon")
                        wait(1)
                    end
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Soul Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Soul Fruit") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit","Soul-Soul")
                        wait(1)
                    end
                end
            end
        end)
        Shop_Fruit:AddToggle("Bring Fruit",_G.Setting_table.BringFruit,function(vu)
            BringFruit = vu
            _G.Setting_table.BringFruit = vu
            savesetting()
        end)
        spawn(function()
            while wait(.2) do
                if BringFruit then
                    for i,v6 in pairs(game:GetService("Workspace"):GetChildren()) do
                        if v6:IsA ("Tool") and (v6.Handle.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 20000 then
                            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v6.Handle.CFrame
                            v6.Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                        end
                    end
                end
            end
        end)
        spawn(function()
            while wait() do
                if _G.Hop_Bring_Fruit then
                    wait(10)
                    _G.Hop_Bring_Fruit_Ex = true
                end
            end
        end)
        Shop_Fruit:AddToggle("Devil Fruit Sniper",_G.Setting_table.Sniper_Fruit,function(vu)
            Sniper_Fruit = vu
            _G.Setting_table.Sniper_Fruit = vu
            savesetting()
        end)
        local l__Remotes__11 = game.ReplicatedStorage:WaitForChild("Remotes");
        u45 = l__Remotes__11.CommF_:InvokeServer("GetFruits");
        Table_DevilFruitSniper = {}
        for i,v in next,u45 do
            table.insert(Table_DevilFruitSniper,v.Name)
        end
        if _G.Setting_table.Select_Fruit == nil then
            _G.Setting_table.Select_Fruit = "..."
        end
        Shop_Fruit:AddDropdown("Select Devil Fruit Sniper",Table_DevilFruitSniper,_G.Setting_table.Select_Fruit,_G.Setting_table.Select_Fruit,function(ply) 
            _G.Select_Fruit = ply
            _G.Setting_table.Select_Fruit = ply
            savesetting()
        end)
        
        Shop_Melee:AddButton("Buy Electro",function()
            local args = {
                [1] = "BuyElectro"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        Shop_Melee:AddButton("Buy Black Leg",function()
            local args = {
                [1] = "BuyBlackLeg"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        Shop_Melee:AddButton("Buy Fishman Karate",function()
            local args = {
                [1] = "BuyFishmanKarate"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        
        Shop_Melee:AddButton("Buy Dragon Claw",function()
            local args = {
                [1] = "BlackbeardReward",
                [2] = "DragonClaw",
                [3] = "1"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            local args = {
                [1] = "BlackbeardReward",
                [2] = "DragonClaw",
                [3] = "2"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        Shop_Melee:AddLabel("")
        Shop_Melee:AddButton("Buy Superhuman",function()
            local args = {
                [1] = "BuySuperhuman"
            }
        
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        
        Shop_Melee:AddButton("Buy Death Step",function()
            local args = {
                [1] = "BuyDeathStep"
            }
        
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        
        Shop_Melee:AddButton("Buy Shakman Karate",function()
            local args = {
                [1] = "BuySharkmanKarate",
                [2] = true
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            local args = {
                [1] = "BuySharkmanKarate"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        Shop_Melee:AddButton("Buy ElectricClaw",function()
            local args = {
                [1] = "BuyElectricClaw"
                }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        
            Shop_Melee:AddButton("Buy Dragon Talon",function()
                local args = {
                    [1] = "BuyDragonTalon",
                    [2] = true
                    }
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                local args = {
                    [1] = "BuyDragonTalon"
                    }
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end)
        
            Shop_M:AddButton("Buy Random Surprise",function()
                local args = {
                    [1] = "Bones",
                    [2] = "Check"
                }
                
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        
                local args = {
                    [1] = "Bones",
                    [2] = "Buy",
                    [3] = 1,
                    [4] = 1
                }
                
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            end)
            
            Shop_M:AddToggle("Auto Buy Random Surprise",_G.Setting_table.Auto_Random,function(vu)
                _G.Auto_Random = vu
                _G.Setting_table.Auto_Random = vu
                savesetting()
            end)
            
            spawn(function()
                while wait(0.3) do
                    if _G.Auto_Random then
                        local args = {
                            [1] = "Bones",
                            [2] = "Check"
                        }
                        
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                        -- Script generated by SimpleSpy - credits to exx#9394
                        
                        local args = {
                            [1] = "Bones",
                            [2] = "Buy",
                            [3] = 1,
                            [4] = 1
                        }
                        
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                    end
                end
            end)
        
        Shop_Sword:AddButton("Buy Katana",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Katana")
        end)
        Shop_Sword:AddButton("Buy Cutlass",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cutlass")
        end)
        Shop_Sword:AddButton("Buy Duel Katana",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Duel Katana")
        end)
        Shop_Sword:AddButton("Buy Iron Mace",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Iron Mace")
        end)
        Shop_Sword:AddButton("Buy Pipe",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Pipe")
        end)
        Shop_Sword:AddButton("Buy Triple Katana",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Triple Katana")
        end)
        Shop_Sword:AddButton("Buy Dual-Headed Blade",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual-Headed Blade")
        end)
        Shop_Sword:AddButton("Buy Bisento",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Bisento")
        end)
        Shop_Sword:AddButton("Buy Soul Cane",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Soul Cane")
        end)
        
        Shop_Gun:AddButton("Buy Slingshot",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Slingshot")
        end)
        Shop_Gun:AddButton("Buy Musket",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Musket")
        end)
        Shop_Gun:AddButton("Buy Fintlock",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Flintlock")
        end)
        Shop_Gun:AddButton("Buy Refined Flintlock",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Refined Flintlock")
        end)
        Shop_Gun:AddButton("Buy Cannon",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cannon")
        end)
        Shop_Gun:AddButton("Buy Kabucha",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","1")
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","2")
        end)
        
        Shop_F:AddButton("Buy Refund Stat",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","1")
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","2")
        end)
        Shop_F:AddButton("Buy Random Ability",function()
            local args = {
                [1] = "BlackbeardReward",
                [2] = "Reroll",
                [3] = "2"
            }
            
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end)
        
        spawn(function()
            while wait(2) do
                if BuyFruitSinper then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PurchaseRawFruit",_G.Setting_table.SelectDevil)
                end 
            end
        end)
        
        if Old_World then
        
            ISland_W:AddButton("Teleport to World 2", function()
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
            end)
        
            ISland_W:AddButton("Teleport to World 3", function()
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
            end)
        
        
            ISland_I:AddButton("Jones Salad", function()
                TP2(CFrame.new(1042.1501464844, 16.299360275269, 1444.3442382813))
            end)
        
            ISland_I:AddButton("Marine1", function()
                TP2(CFrame.new(-2599.6655273438, 6.9146227836609, 2062.2216796875))
            end)
        
            ISland_I:AddButton("Marine2", function()
                TP2(CFrame.new(-5081.3452148438, 85.221641540527, 4257.3588867188))
            end)
        
            ISland_I:AddButton("Midle Town", function()
                TP2(CFrame.new(-655.97088623047, 7.878026008606, 1573.7612304688))
            end)
        
            ISland_I:AddButton("Jungle", function()
                TP2(CFrame.new(-1499.9877929688, 22.877912521362, 353.87060546875))
            end)
        
            ISland_I:AddButton("Pirate Village", function()
                TP2(CFrame.new(-1163.3889160156, 44.777843475342, 3842.8276367188))
            end)
        
            ISland_I:AddButton("Desert", function()
                TP2(CFrame.new(954.02056884766, 6.6275520324707, 4262.611328125))
            end)
        
            ISland_I:AddButton("Frozen Village", function()
                TP2(CFrame.new(1144.5270996094, 7.3292083740234, -1164.7322998047))
            end)
        
            ISland_I:AddButton("Colosseum", function()
                TP2(CFrame.new(-1667.5869140625, 39.385631561279, -3135.5817871094))
            end)
        
            ISland_I:AddButton("Prison", function()
                TP2(CFrame.new(4857.6982421875, 5.6780304908752, 732.75750732422))
            end)
        
            ISland_I:AddButton("Mob Leader", function()
                TP2(CFrame.new(-2841.9604492188, 7.3560485839844, 5318.1040039063))
            end)
        
            ISland_I:AddButton("Magma Village", function()
                TP2(CFrame.new(-5328.8740234375, 8.6164798736572, 8427.3994140625))
            end)
        
            ISland_I:AddButton("UnderWater Gate", function()
                TP2(CFrame.new(3893.953125, 5.3989524841309, -1893.4851074219))
            end)
        
            ISland_I:AddButton("UnderWater City", function()
                TP2(CFrame.new(61191.12109375, 18.497436523438, 1561.8873291016))
            end)
        
            ISland_I:AddButton("Fountain City", function()
                TP2(CFrame.new(5244.7133789063, 38.526943206787, 4073.4987792969))
            end)
        
            ISland_I:AddButton("Sky1", function()
                TP2(CFrame.new(-4878.0415039063, 717.71246337891, -2637.7294921875))
            end)
        
            ISland_I:AddButton("Sky2", function()
                TP2(CFrame.new(-7899.6157226563, 5545.6030273438, -422.21798706055))
            end)
        
            ISland_I:AddButton("Sky3", function()
                TP2(CFrame.new(-7868.5288085938, 5638.205078125, -1482.5548095703))
            end)
        
        elseif New_World then
                
            ISland_W:AddButton("Teleport to World 1", function()
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
            end)
        
            ISland_W:AddButton("Teleport to World 3", function()
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
            end)
        
        
            ISland_I:AddButton("Dock", function()
                TP2(CFrame.new(-12.519311904907, 19.302536010742, 2827.853515625))
            end)
        
            ISland_I:AddButton("Mansion", function()
                TP2(CFrame.new(-390.34829711914, 321.89730834961, 869.00506591797))
            end)
        
            ISland_I:AddButton("Kingdom Of Rose", function()
                TP2(CFrame.new(-388.29895019531, 138.35575866699, 1132.1662597656))
            end)
        
            ISland_I:AddButton("Cafe", function()
                TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
            end)
        
            ISland_I:AddButton("Sunflower Field", function()
                TP2(CFrame.new(-1576.7171630859, 198.61849975586, 13.725157737732))
            end)
        
            ISland_I:AddButton("Jeramy Mountain", function()
                TP2(CFrame.new(1986.3519287109, 448.95678710938, 796.70239257813))
            end)
        
            ISland_I:AddButton("Colossuem", function()
                TP2(CFrame.new(-1871.8974609375, 45.820514678955, 1359.6843261719))
            end)
        
            ISland_I:AddButton("Factory", function()
                TP2(CFrame.new(349.53750610352, 74.446998596191, -355.62420654297))
            end)
        
            ISland_I:AddButton("The Bridge", function()
                TP2(CFrame.new(-1860.6354980469, 88.384948730469, -1859.1593017578))
            end)
        
            ISland_I:AddButton("Green Bit", function()
                TP2(CFrame.new(-2202.3706054688, 73.097663879395, -2819.2687988281))
            end)
        
            ISland_I:AddButton("Graveyard", function()
                TP2(CFrame.new(-5617.5927734375, 492.22183227539, -778.3017578125))
            end)
        
            ISland_I:AddButton("Dark Area", function()
                TP2(CFrame.new(3464.7700195313, 13.375151634216, -3368.90234375))
            end)
        
            ISland_I:AddButton("Snow Mountain", function()
                TP2(CFrame.new(561.23834228516, 401.44781494141, -5297.14453125))
            end)
        
            ISland_I:AddButton("Hot Island", function()
                TP2(CFrame.new(-5505.9633789063, 15.977565765381, -5366.6123046875))
            end)
        
            ISland_I:AddButton("Cold Island", function()
                TP2(CFrame.new(-5924.716796875, 15.977565765381, -4996.427734375))
            end)
        
            ISland_I:AddButton("Ice Castle", function()
                TP2(CFrame.new(6111.7109375, 294.41259765625, -6716.4829101563))
            end)
        
            ISland_I:AddButton("Usopp's Island", function()
                TP2(CFrame.new(4760.4985351563, 8.3444719314575, 2849.2426757813))
            end)
        
            ISland_I:AddButton("inscription Island", function()
                TP2(CFrame.new(-5099.01171875, 98.241539001465, 2424.4035644531))
            end)
        
            ISland_I:AddButton("Forgotten Island", function()
                TP2(CFrame.new(-3051.9514160156, 238.87203979492, -10250.807617188))
            end)
        
            ISland_I:AddButton("Ghost Ship", function()
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
            end)
        
            ISland_I:AddButton("Mini Sky", function()
                TP2(CFrame.new(-262.11901855469, 49325.69140625, -35272.49609375))
            end)
        
        elseif Three_World  then
        
            ISland_W:AddButton("Teleport to World 1", function()
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
            end)
        
            ISland_W:AddButton("Teleport to World 2", function()
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
            end)
        
        
            ISland_I:AddButton("Port Town", function()
                TP2(CFrame.new(-275.21615600586, 43.755737304688, 5451.0659179688))
            end)
        
            ISland_I:AddButton("Hydra Island", function()
                TP2(CFrame.new(5541.2685546875, 668.30456542969, 195.48069763184))
            end)
            
            ISland_I:AddButton("Gaint Tree", function()
                TP2(CFrame.new(2276.0859375, 25.87850189209, -6493.03125))
            end)
            
            ISland_I:AddButton("Zou Island", function()
                TP2(CFrame.new(-10034.40234375, 331.78845214844, -8319.6923828125))
            end)
            
            ISland_I:AddButton("PineApple Village", function()
                TP2(CFrame.new(-11172.950195313, 331.8049621582, -10151.033203125))
            end)
            
            ISland_I:AddButton("Mansion", function()
                TP2(CFrame.new(-12548.998046875, 332.40396118164, -7603.1865234375))
            end)
        
            ISland_I:AddButton("Castle on the Sea", function()
                TP2(CFrame.new(-5498.0458984375, 313.79473876953, -2860.6022949219))
            end)
        
            ISland_I:AddButton("Graveyard Island", function()
                TP2(CFrame.new(-9515.07324, 142.130615, 5537.58398))
            end)
            ISland_I:AddButton("Haunted Castle",function()
                TP2(CFrame.new(-8932.86, 143.258, 6063.31))
            end)
            ISland_I:AddButton("Raid Lab", function()
                TP2(CFrame.new(-5057.146484375, 314.54132080078, -2934.7995605469))
            end)
        
            ISland_I:AddButton("Mini Sky", function()
                TP2(CFrame.new(-263.66668701172, 49325.49609375, -35260))
            end)
            ISland_I:AddButton("Ice Cream Island",function()
                TP2(CFrame.new(-691.829, 371.943, -11106.4))
            end)
            ISland_I:AddButton("Soa of Cake",function()
                TP2(CFrame.new(-2073.262451171875, 37.16134262084961, -10183.3271484375))
            end)
            ISland_I:AddButton("Cake Loaf",function()
                TP2(CFrame.new(-2099.33, 66.9971, -12128.6))
            end)
        end
        
        AutoFarm_Item:AddToggle("Auto Buy Legendary Sword",_G.Setting_table.Auto_Buy_Legendary_Sword,function(vu)
            Auto_Buy_Legendary_Sword = vu
            _G.Setting_table.Auto_Buy_Legendary_Sword = vu
            savesetting()
        end)
        spawn(function()
            while wait(.1) do
                if Auto_Buy_Legendary_Sword then
                    local args = {
                        [1] = "LegendarySwordDealer",
                        [2] = "2"
                    }
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                end
            end
        end)
        spawn(function()
            while wait() do
                if _G.Hop_Buy_Legendary_Sword then
                    wait(7)
                    _G.Hop_Buy_Legendary_Sword_Ex = true
                end
            end
        end)
        F = "❌"
        T = "✅"
        game:GetService("Players").LocalPlayer.PlayerGui.Main.Inventory.Visible = true
        wait(1)
        for i,v in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main.Inventory.Container.Stored.ScrollingFrame.Frame:GetChildren()) do
            if v.Name == "Shisui" then
                _G.Setting_table.Shisui = true
                savesetting()
            end
            if v.Name == "Saddi" then
                _G.Setting_table.Saddi = true
                savesetting()
            end
            if v.Name == "Wando" then
                _G.Setting_table.Wando = true
                savesetting()
            end
        end
        if game.Players.LocalPlayer.Character:FindFirstChild("Shisui") or game.Players.LocalPlayer.Backpack:FindFirstChild("Shisui") or _G.Setting_table.Shisui then
            Shisui = T
        else
            Shisui = F
        end
        if game.Players.LocalPlayer.Character:FindFirstChild("Saddi") or game.Players.LocalPlayer.Backpack:FindFirstChild("Saddi") or _G.Setting_table.Saddi then
            Saddi = T
        else
            Saddi = F
        end
        if game.Players.LocalPlayer.Character:FindFirstChild("Wando") or game.Players.LocalPlayer.Backpack:FindFirstChild("Wando") or _G.Setting_table.Wando then
            Wando = T
        else
            Wando = F
        end
        game:GetService("Players").LocalPlayer.PlayerGui.Main.Inventory.Visible = false
        AutoFarm_Item:AddLabel(tostring(Shisui).." : Shisui")
        AutoFarm_Item:AddLabel(tostring(Saddi).." : Saddi")
        AutoFarm_Item:AddLabel(tostring(Wando).." : Wando")
        
        Status_I:AddButton("Open Inventory",function()
            game:GetService("Players").LocalPlayer.PlayerGui.Main.Inventory.Visible = true 
        end)
        Status_I:AddButton("Open Fruit Inventory",function()
            game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Visible = true
        end)
        Status_I:AddButton("Open Shop Fruit",function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits")
            game.Players.localPlayer.PlayerGui.Main.FruitShop.Visible = true
        end)
        Status_I:AddButton("Open Color Haki",function()
            game.Players.localPlayer.PlayerGui.Main.Colors.Visible = true
        end)
        Status_I:AddButton("Open Fruit Awaken",function()
            game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler.Visible = true
        end)
        Status_I:AddButton("Open Title Name", function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getTitles")
            game.Players.localPlayer.PlayerGui.Main.Titles.Visible = true
        end)
        Status_I:AddLabel("")
        Status_I:AddButton("Join Pirates Team", function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetTeam","Pirates") 
        end)
        Status_I:AddButton("Join Marines Team", function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetTeam","Marines") 
        end)
        
        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2 then
            Race_Evo = "3"
        elseif _G.Setting_table.Ability_Mink_V2 == false then
            Race_Evo = "2"
        elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == -2 or _G.Setting_table.Ability_Mink_V1 then
            Race_Evo = "1"
        else
            Race_Evo = "0"
        end
        Ken_Haki = 0
        
        Status_S:AddLabel("Race : "..tostring(game.Players.LocalPlayer.Data.Race.Value))
        Status_S:AddLabel("Race Evo : "..Race_Evo.."/3")
        local O_H = Status_S:AddLabel("Observation/ Haki : "..tostring(Ken_Haki).."/5000")
        spawn(function()
            while wait() do
                if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Buy") == 0 then
                else
                    OPP = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Status")
                    Lpp = string.match(tostring(OPP), "%d+")
                    O_H:Set("Observation Haki : "..tostring(Lpp).."/5000")
                    wait(10)
                end
            end
        end)
        
        Race_S:AddToggle("Auto Evo Race V1",_G.Setting_table.Ability_Mink_V1,function(vu)
            Ability_Mink_V1 = vu
            _G.Setting_table.Ability_Mink_V1 = vu
            savesetting()
        end)
        spawn(function()
            while wait() do
                if Ability_Mink_V1 then
                    if PO then
                    else
                        repeat wait(.1)
                            TP2(CFrame.new(-2776.486328125, 73.46427917480469, -3568.610595703125))
                        until (Vector3.new(-2776.486328125, 73.46427917480469, -3568.610595703125)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 3 or Ability_Mink_V1 == false
                    end
                    wait(1)
                    pcall(function()
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
                    end)
                    if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") then
                        spawn(function()
                            game.StarterGui:SetCore("SendNotification", {
                                     Title = "Auto Ability", 
                                     Text = "กำลังหา ดอกไม้น้ำเงิน",
                                     Icon = "http://www.roblox.com/asset/?id=9370135749",
                                     Duration = 3
                               })
                           wait(5)
                        end)
                        repeat wait(3)
                            TP2(game:GetService("Workspace"):FindFirstChild("Flower1").CFrame)
                        until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 1") or Ability_Mink_V1 == false
                    end
                    if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") then
                        spawn(function()
                            game.StarterGui:SetCore("SendNotification", {
                                     Title = "Auto Ability", 
                                     Text = "กำลังหา ดอกไม้แดง",
                                     Icon = "http://www.roblox.com/asset/?id=9370135749",
                                     Duration = 3
                               })
                           wait(5)
                        end)
                        repeat wait(3)
                            TP2(game:GetService("Workspace"):FindFirstChild("Flower2").CFrame)
                        until game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") or game.Players.LocalPlayer.Character:FindFirstChild("Flower 2") or Ability_Mink_V1 == false
                    end
                    if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game.Players.LocalPlayer.Character:FindFirstChild("Flower 3") then
                        spawn(function()
                            game.StarterGui:SetCore("SendNotification", {
                                     Title = "Auto Ability", 
                                     Text = "กำลังหา ดอกไม้เหลือง",
                                     Icon = "http://www.roblox.com/asset/?id=9370135749",
                                     Duration = 3
                               })
                           wait(5)
                        end)
                        PO = true
                        if game:GetService("Workspace").Enemies:FindFirstChild("Marine Captain [Lv. 900]") then
                            StatrMagnet = false
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == "Marine Captain [Lv. 900]" then
                                    CFrameMon = v.HumanoidRootPart.Position
                                    _G.PosMon = v.HumanoidRootPart.CFrame
                                    StatrMagnet = true
                                    Clip = true
                                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                        if tostring(v2.ToolTip) == "Melee" then
                                            Melee_E = v2.Name
                                        end
                                    end
                                    v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                    repeat wait()
                                        pcall(function()
                                            EquipWeapon(Melee_E)
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                            game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                                            TP(v.HumanoidRootPart.CFrame*CFrame.new(0,25,0))
                                        end)
                                    until v.Humanoid.Health <= 0 or not v.Parent or Ability_Mink_V1 == false or game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3")
                                    Clip = false
                                end
                            end
                        else
                            TP2(CFrame.new(-2335.2026367188, 79.786659240723, -3245.8674316406))
                        end
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") then
                        repeat wait(.1)
                            TP2(CFrame.new(-2776.486328125, 73.46427917480469, -3568.610595703125))
                        until (Vector3.new(-2776.486328125, 73.46427917480469, -3568.610595703125)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 3 or Ability_Mink_V1 == false
                        local args = {
                            [1] = "Alchemist",
                            [2] = "1"
                        }
                        
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                        local args = {
                            [1] = "Alchemist",
                            [2] = "3"
                        }
                        
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
                        wait(2)
                        _G.Setting_table.Ability_Mink_V1 = false
                        savesetting()
                        game.Players.LocalPlayer:Kick("ฟามเผ่า V1 เสร็จแล้วว")
                    end
                end
            end
        end)
        Race_S:AddToggle("Auto Evo Race V2",_G.Setting_table.Ability_Mink_V2,function(vu)
            Ability_Mink_V2 = vu
            _G.Setting_table.Ability_Mink_V2 = vu
            savesetting()
        end)
        spawn(function()
            while wait() do
                if Ability_Mink_V2 then
                    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") ~= 0 then
                        spawn(function()
                            game.StarterGui:SetCore("SendNotification", {
                                     Title = "Auto Ability", 
                                     Text = "กำลังหาผล ราคา 1 ล้าน+",
                                     Icon = "http://www.roblox.com/asset/?id=9370135749",
                                     Duration = 3
                               })
                           wait(10)
                        end)
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Quake Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Human: Buddha Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("String Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Bird: Phoenix Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Rumble Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Paw Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Gravity Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Dough Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Shadow Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Venom Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Control Fruit") or game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Quake Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Human: Buddha Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("String Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Bird: Phoenix Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Rumble Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Paw Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Gravity Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Dough Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Shadow Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Venom Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Control Fruit") or game.Players.LocalPlayer.Character:FindFirstChild("Dragon Fruit") then
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1")
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","2")
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","3")
                        end
                    else
                        spawn(function()
                            game.StarterGui:SetCore("SendNotification", {
                                     Title = "Auto Ability", 
                                     Text = "กำลังหา บอส โดฟามิงโก้",
                                     Icon = "http://www.roblox.com/asset/?id=9370135749",
                                     Duration = 3
                               })
                           wait(10)
                        end)
                        if (Vector3.new(2191.1674804688, 15.177842140198, 694.69873046875)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 10 then
                            if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
                                for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                    if tostring(v2.ToolTip) == "Melee" then
                                        Melee_E = v2.Name
                                    end
                                end
                                game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.Size = Vector3.new(50,50,50)
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                                repeat wait()
                                    if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").Humanoid.Health <= 0 or not game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
                                        wait(2)
                                        _G.Setting_table.Ability_Mink_V2 = false
                                        Ability_Mink_V2 = false
                                        savesetting()
                                        game.Players.LocalPlayer:Kick("\nฟามเผ่า V2 เสร็จแล้วว")
                                        game:GetService('TeleportService'):Teleport(game.PlaceId)
                                    end
                                    EquipWeapon(Melee_E)
                                    TP(game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,-10,0))
                                    game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                    game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                                until game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").Humanoid.Health <= 0 or not game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or Ability_Mink_V2 == false
                                if game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]").Humanoid.Health <= 0 or not game:GetService("Workspace").Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
                                        wait(2)
                                        _G.Setting_table.Ability_Mink_V2 = false
                                        Ability_Mink_V2 = false
                                        savesetting()
                                        game.Players.LocalPlayer:Kick("\nฟามเผ่า V2 เสร็จแล้วว")
                                        game:GetService('TeleportService'):Teleport(game.PlaceId)
                                    end
                            else
                                game.StarterGui:SetCore("SendNotification", {
                                    Title = "Auto Ability", 
                                    Text = "รอบอสเกิด",
                                    Icon = "http://www.roblox.com/asset/?id=9370135749",
                                    Duration = 3
                              })
                          wait(10)
                            end
                        else
                            repeat wait()
                                TP2(CFrame.new(2191.1674804688, 15.177842140198, 694.69873046875))
                            until (Vector3.new(2191.1674804688, 15.177842140198, 694.69873046875)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 20
                        end
                    end
                end
            end
        end)
        
        Race_E:AddToggle("Auto Evo Mink V3",_G.Setting_table.Ability_Mink_V3,function(vu)
            Ability_Mink_V3 = vu
            _G.Setting_table.Ability_Mink_V3 = vu
            savesetting()
            if Ability_Mink_V3 then
                repeat wait()
                    TP2(CFrame.new(-385.250916, 73.0458984, 297.388397))
                until (Vector3.new(-385.250916, 73.0458984, 297.388397)-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 10
            end
            if Ability_Mink_V3 then
                if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
                    Bartlio_Farm = false
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","2")
                else
                    Bartlio_Farm = true
                end
            end
        end)
        spawn(function()
            while wait() do
                if Ability_Mink_V3 then
                    if New_World then
                        if not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Agility") then
                            --game.Players.LocalPlayer.Character.Stun.Value = 0
                            game.Players.LocalPlayer.Character.Humanoid.Sit = false
                            --game.Players.LocalPlayer.Character.Busy.Value = false1
                        elseif game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Agility") then
                            Ability_Mink_V3 = false
                            _G.Setting_table.Ability_Mink_V3 = false
                            savesetting()
                            game.Players.LocalPlayer:Kick("\nทำเผ่าวี 3 เสร็จแล้ว")
                        end
                    else
                        game.StarterGui:SetCore("SendNotification", {
                            Title = "New World", 
                            Text = "คุณต้องไปโลก 2 ครับ",
                            Icon = "http://www.roblox.com/asset/?id=9370135749",
                            Duration = 3
                        })
                    end
                end
            end
        end)
        
        spawn(function()
            while wait() do
                if Ability_Mink_V3 then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Ability") then
                        game.Players.LocalPlayer:Kick("\nฟามเผ่า วี3 เสร็จแล้ว")
                    end
                    TP_CH()
                    wait(2)
                    TP_CH()
                    wait(2)
                    TP_CH()
                    wait(2)
                    TP_CH()
                    wait(2)
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","3")
                end
            end
        end)
        
        function TP_CH()
            for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
                if TPO == nil then
                    if v.Name == "Chest1" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                        TPO = true
                        repeat wait()
                            TP2(v.CFrame)
                        until not v.Parent or Ability_Mink_V3 == false
                        TPO = nil
                    elseif v.Name == "Chest2" and (v.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                        TPO = true
                        repeat wait()
                            TP2(v.CFrame)
                        until not v.Parent or Ability_Mink_V3 == false
                        TPO = nil
                    else
                        TPO = nil
                        TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
                    end
                end
            end
        end
        
        Race_E:AddToggle("Auto Evo Skypie V3",_G.Setting_table.Ability_Skypie_V3,function(vu)
            Ability_Skypie_V3 = vu
            _G.Setting_table.Ability_Skypie_V3 = vu
            savesetting()
            if Ability_Skypie_V3 then
                if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
                    Bartlio_Farm = false
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","2")
                else
                    Bartlio_Farm = true
                end
            end
        end)
        
        spawn(function()
            while wait() do
                if Ability_Skypie_V3 then
                    if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1") == -2 then
                        game.Players.LocalPlayer:Kick("\nฟามเผ่า วี3 เสร็จแล้ว")
                    end
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","3")
                end
            end
        end)
        
        spawn(function()
            while wait() do
                pcall(function()
                    if Ability_Skypie_V3 then
                        for i,v in pairs(game.Workspace.Character:GetChildren()) do
                            if (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 500 then
                                _G.PVP = v
                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1000 then
                                _G.PVP = v
                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 1500 then
                                _G.PVP = v
                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 2000 then
                                _G.PVP = v
                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 3000 then
                                _G.PVP = v
                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude < 4200 then
                                _G.PVP = v
                            elseif (v.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 4200 then
                                _G.PVP = v
                            end
                            for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                                if tostring(v2.ToolTip) == "Melee" then
                                    Melee_E = v2.Name
                                end
                            end
                            repeat wait()
                                spawn(function()
                                    if (_G.PVP.HumanoidRootPart.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 100 then
                                        wait(10)
                                        if _G.PVP.Humanoid.Health == _G.PVP.Humanoid.MaxHealth then
                                            v:Destroy()
                                            None = true
                                        end
                                    end
                                end)
                                EquipWeapon(Melee_E)
                                TP(_G.PVP.HumanoidRootPart.CFrame*CFrame.new(0,30,0))
                                game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                            until _G.PVP.Humanoid.Health <= 0 or not _G.PVP.Parent or Ability_Skypie_V3 == false or None
                            None = false
                        end
                    end
                end)
            end
        end)
        Race_E:AddToggle("Auto Evo Human V3",_G.Setting_table.Ability_Human_V3,function(vu)
            Ability_Human_V3 = vu
            _G.Setting_table.Ability_Human_V3 = vu
            savesetting()
            if Ability_Human_V3 then
                if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
                    _G.AutoBartiloBring = false
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","2")
                else
                    _G.AutoBartiloBring = true
                end
            end
        end)
        spawn(function()
            while wait() do
                if Ability_Human_V3 then
                    for i2,v2 in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
                        if tostring(v2.ToolTip) == "Melee" then
                            Melee_E = v2.Name
                        end
                    end
                    _G.SelectBoss = "Jeremy [Lv. 850] [Boss]"
                    CheckQuestBoss()
                    if game:GetService("ReplicatedStorage"):FindFirstChild("Jeremy [Lv. 850] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
                        repeat wait()
                            TP2(CFrameBoss)
                        until (CFrameBoss.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5
                        wait(4)
                        if game:GetService("Workspace").Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
                            repeat wait()
                                game:GetService("Workspace").Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]").HumanoidRootPart.Size = Vector3.new(50,50,50)
                                EquipWeapon(Melee_E)
                                TP(game:GetService("Workspace").Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,-20,0))
                                game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                            until game:GetService("Workspace").Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]").Humanoid.Health <= 0 or not game:GetService("Workspace").Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") or Ability_Human_V3 == false
                        end
                    else
                        spawn(function()
                            game.StarterGui:SetCore("SendNotification", {
                                         Title = "Auto Evo Race", 
                                         Text = "รอบอสเกิด",
                                         Icon = "http://www.roblox.com/asset/?id=9370135749",
                                         Duration = 3
                                   })
                        end)
                        wait(5)
                    end
                    _G.SelectBoss = "Fajita [Lv. 925] [Boss]"
                    CheckQuestBoss()
                    if game:GetService("ReplicatedStorage"):FindFirstChild("Fajita [Lv. 925] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Fajita [Lv. 925] [Boss]") then
                        repeat wait()
                            TP2(CFrameBoss)
                        until (CFrameBoss.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5
                        wait(4)
                        if game:GetService("Workspace").Enemies:FindFirstChild("Fajita [Lv. 925] [Boss]") then
                            repeat wait()
                                game:GetService("Workspace").Enemies:FindFirstChild("Fajita [Lv. 925] [Boss]").HumanoidRootPart.Size = Vector3.new(50,50,50)
                                EquipWeapon(Melee_E)
                                TP(game:GetService("Workspace").Enemies:FindFirstChild("Fajita [Lv. 925] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,-20,0))
                                game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                            until game:GetService("Workspace").Enemies:FindFirstChild("Fajita [Lv. 925] [Boss]").Humanoid.Health <= 0 or not game:GetService("Workspace").Enemies:FindFirstChild("Fajita [Lv. 925] [Boss]") or Ability_Human_V3 == false
                        end
                    else
                        spawn(function()
                            game.StarterGui:SetCore("SendNotification", {
                                         Title = "Auto Evo Race", 
                                         Text = "รอบอสเกิด",
                                         Icon = "http://www.roblox.com/asset/?id=9370135749",
                                         Duration = 3
                                   })
                        end)
                        wait(5)
                    end
                    _G.SelectBoss = "Diamond [Lv. 750] [Boss]"
                    CheckQuestBoss()
                    if game:GetService("ReplicatedStorage"):FindFirstChild("Diamond [Lv. 750] [Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Diamond [Lv. 750] [Boss]") then
                        repeat wait()
                            TP2(CFrameBoss)
                        until (CFrameBoss.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5
                        wait(5)
                        if game:GetService("Workspace").Enemies:FindFirstChild("Diamond [Lv. 750] [Boss]") then
                            repeat wait()
                                game:GetService("Workspace").Enemies:FindFirstChild("Diamond [Lv. 750] [Boss]").HumanoidRootPart.Size = Vector3.new(50,50,50)
                                EquipWeapon(Melee_E)
                                TP(game:GetService("Workspace").Enemies:FindFirstChild("Diamond [Lv. 750] [Boss]").HumanoidRootPart.CFrame*CFrame.new(0,-20,0))
                                game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                            until game:GetService("Workspace").Enemies:FindFirstChild("Diamond [Lv. 750] [Boss]").Humanoid.Health <= 0 or not game:GetService("Workspace").Enemies:FindFirstChild("Diamond [Lv. 750] [Boss]") or Ability_Human_V3 == false
                        end
                    else
                        spawn(function()
                            game.StarterGui:SetCore("SendNotification", {
                                         Title = "Auto Evo Race", 
                                         Text = "รอบอสเกิด",
                                         Icon = "http://www.roblox.com/asset/?id=9370135749",
                                         Duration = 3
                                   })
                        end)
                        wait(5)
                    end
                end
            end
        end)
        
        Race_E:AddToggle("Auto Evo Fishman V3",_G.Setting_table.Ability_Fish_V3,function()
            Ability_Fish_V3 = vu
            _G.Setting_table.Ability_Fish_V3 = vu
            savesetting()
            if Ability_Fish_V3 then
                if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
                    _G.AutoBartiloBring = false
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","2")
                else
                    _G.AutoBartiloBring = true
                end
            end
        end)
        spawn(function()
            while wait(2) do
                if Ability_Fish_V3 then
                    pcall(function()
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Ability") then
                            Ability_Fish_V3 = false
                            _G.Setting_table.Ability_Fish_V3 = false
                            savesetting()
                            game.Players.LocalPlayer:Kick("\nฟามเผ่า วี3 เสร็จแล้ว")
                        end
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","1")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Wenlocktoad","3")
                    end)
                end
            end
        end)
        
        spawn(function()
            while wait() do
                if Ability_Fish_V3 then
                    spawn(function()
                        game.StarterGui:SetCore("SendNotification", {
                            Title = "Auto Ability", 
                            Text = "กำลังหา เจ้าทะเล",
                            Icon = "http://www.roblox.com/asset/?id=9370135749",
                            Duration = 4
                       })
                    end)
                     
                    for i,v in pairs(game:GetService("Workspace").SeaBeasts:GetChildren()) do
                        Hop = false
                        if v:FindFirstChild("HumanoidRootPart") then
                            Hop = true
                            Clip = true
                            repeat wait()
                                TP2(v.HumanoidRootPart.CFrame * CFrame.new(0,100,0))
                                game:GetService'VirtualUser':Button1Down(Vector2.new(9,9))
                                game:GetService'VirtualUser':Button1Up(Vector2.new(9,9))
                            until not v.Parent or Ability_Fish_V3 == false
                            Clip = false
                            Hop = false
                        end
                    end
                end
            end
        end)
        
        Lp = 500
        local K_C_M = Status_K:AddLabel("Kill Cake Monster : "..Lp.."/500")
        if Three_World then
            _G.Lip = true
        end
        spawn(function()
            while _G.Lip do wait(5)
                OP = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CakePrinceSpawner")
                Lp = tonumber(string.match(tostring(OP), "%d+"))
                if Lp > 0 then
                    K_C_M:Set("Kill Cake Monster : "..tostring(Lp).."/500")
                else
                    K_C_M:Set("Kill Cake Monster : 0/500")
                end
            end
        end)
        B_H = "0"
        local Bone_S = Status_B:AddLabel("Bone 🦴 : "..B_H)
        _G.F = "❌"
        _G.T = "✅"
        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Check") == 0 then
            _G.K = _G.F
        else
            _G.K = _G.T
        end
        if Three_World then
            B_H = string.match(tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Bones", "Check")), "%d+")
            spawn(function()
                while wait(.1) do
                    B_H = string.match(tostring(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Bones", "Check")), "%d+")
                    Bone_S:Set("Bone 🦴 : "..tostring(B_H))
                    wait(7)
                end
            end)
        end
        local KoP = Status_B:AddLabel("Buy : ".._G.K)
        spawn(function()
            while wait(1) do
                if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Check") == 0 then
                    _G.K = _G.F
                else
                    _G.K = _G.T
                end
                KoP:Set("Buy : ".._G.K)
                wait(5)
            end
        end)
        AutoFarm_Misc:AddToggle("Auto Buso Haki",true,function(vu)
            Auto_Haki = vu
        end)
        spawn(function()
            while wait(1) do
                if Auto_Haki then
                    if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
                    end
                end
            end
        end)
        AutoFarm_Misc:AddToggle("Auto Ken Haki",true,function(vu)
            Auto_Ken = vu
        end)
        spawn(function()
            while wait(2) do
                if Auto_Ken then
                    game:GetService("ReplicatedStorage").Remotes.CommE:FireServer("Ken",true)
                    wait(3)
                end
            end
        end)
        
        AutoFarm_Misc:AddToggle("Auto Set Spawn",true,function(vu)
            Spawn_Set = vu
            _G.Setting_table.Spawn_Set = vu
            savesetting()
        end)
        spawn(function()
            while wait(5) do
                if Spawn_Set then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
                end
            end
        end)
        ISland_S:AddToggle("Auto Rejoin On Kick!",true,function(vu)
            Rejoin_K = vu
            _G.Setting_table.Rejoin_K = vu
            savesetting()
        end)
        game.CoreGui.RobloxPromptGui.promptOverlay.DescendantAdded:Connect(function()
            local GUI = game.CoreGui.RobloxPromptGui.promptOverlay:FindFirstChild("ErrorPrompt")
            if GUI and TP_Ser == nil and Rejoin_K then
                if GUI.TitleFrame.ErrorTitle.Text == "Disconnected" then
                    if #game.Players:GetPlayers() <= 1 then
                        game.Players.LocalPlayer:Kick("\nRejoining...")
                        wait()
                        game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)
                    else
                        game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, game.JobId, game.Players.LocalPlayer)
                    end
                end
            end
        end)
        ISland_S:AddToggle("Anti AFK",true,function(vu)
            AFK = vu
        end)
        spawn(function()
            game:GetService("Players").LocalPlayer.Idled:connect(function()
                if AFK then
                    VirtualUser:CreateButton2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
                    wait(1)
                    VirtualUser:CreateButton2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
                end
            end)
        end)
        
    end
