✨ Wand UI (Redz Library V5 Remake)

📌 About

Wand UI is a rebuilt and optimized version of Redz Library V5.

It uses the same UI style as the original library, with improvements and refinements for better performance and usability.

The UI is named Wand to represent the next generation of Redz Hub UI systems.

🔹 Information

- Made by real_redz
- Designed mainly for use in Redz Hub scripts
- Open-Source, Lightweight, and Optimized

---

🚀 Getting Started

To load Wand UI, simply run:

local Library = loadstring(game:HttpGet(
    "https://raw.githubusercontent.com/tlredz/Library/refs/heads/main/redz-V5-remake/main.luau"
))()

---

🪟 Creating a Window

local Window = Library:MakeWindow({
    Title = "Nice Hub : Cool Game",
    SubTitle = "dev by real_redz",
    ScriptFolder = "redz-library-V5"
})

---

🧩 Window API

Minimizer

local Minimizer = Window:NewMinimizer({
    KeyCode = Enum.KeyCode.LeftControl
})

local MobileButton = Minimizer:CreateMobileMinimizer({
    Image = "rbxassetid://0",
    BackgroundColor3 = Color3.fromRGB(0, 0, 0)
})

Functions:

- "Cancel()"
- "Minimize()"
- "IsMinimized : boolean"

---

Tabs

Normal

local Tab = Window:MakeTab({
    Title = "Cool Tab",
    Icon = "Home"
})

Compact

local Tab = Window:MakeTab({ "Cool Tab", "Home" })

---

Dialog

Window:Dialog({
    Title = "Hello!",
    Content = "do you like Coffee?",
    Options = {
        { Name = "No" },
        {
            Name = "Yes!",
            Callback = function()
                print("Yes, I like Coffee")
            end
        }
    }
})

---

Notification

Window:Notify({
    Title = "Notification",
    Content = "this is a Notification",
    Image = "rbxassetid://10734953451",
    Duration = 5
})

---

⚙️ Options API

Toggle

Tab:AddToggle({
    Name = "Toggle",
    Default = false,
    Callback = function(Value)
        
    end
})

Button

Tab:AddButton({
    Name = "My Button",
    Debounce = 0.5,
    Callback = function()
        
    end
})

Slider

Tab:AddSlider({
    Name = "Cool Title",
    Min = -5,
    Max = 5,
    Increment = 0.25,
    Default = 0,
    Callback = function(Value)
        
    end
})

Dropdown

Tab:AddDropdown({
    Name = "Dropdown",
    Options = {"one", "two", "three", "four", "five"},
    Default = "one",
    Callback = function(Value)
        
    end
})

Multi Select

Tab:AddDropdown({
    Name = "Dropdown",
    MultiSelect = true,
    Options = {"one", "two", "three", "four", "five"},
    Default = {"one", "four"},
    Callback = function(Value)
        
    end
})

---

TextBox

Tab:AddTextBox({
    Name = "My TextBox",
    Placeholder = "input text...",
    ClearOnFocus = true,
    Callback = function(Value)
        
    end
})

---

Paragraph

Tab:AddParagraph(
    "Paragraph",
    "This is a Paragraph\nSecond Line"
)

---

Discord Invite

MainTab:AddDiscordInvite({
    Title = "redz Hub | Community",
    Description = "A community for redz Hub users.",
    Banner = "rbxassetid://17382040552",
    Logo = "rbxassetid://17382040552",
    Invite = "https://discord.gg/redz-hub",
    Members = 470000,
    Online = 20000
})

---

🔍 UI Scale

- Min Scale: "0.6"
- Max Scale: "1.6"
- Default: "1.0"

Library:SetUIScale(1.0)
print(
    `UI Max Scale is: {Library:GetMaxScale()} and minimum is: {Library:GetMinScale()}`
)

---

🏳️ Flags System

Tab:AddToggle({
    Name = "Cool Toggle",
    Flag = "toggle_flag"
})

local ToggleValue = Window:GetFlag("toggle_flag") or false

Tab:AddToggle({
    Name = "Cool Toggle",
    Default = ToggleValue,
    Callback = function(Value)
        Window:SetFlag("toggle_flag", Value)
    end
})
