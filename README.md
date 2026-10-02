# 📍 Waypoints Data

ملف مخصص لحفظ إحداثيات `Vector3` وترتيبها داخل أقسام، بحيث تقدر تستخدم الإحداثيات بسهولة داخل سكربتات Roblox.

## 📦 محتويات الملف

الإحداثيات تكون مرتبة بهذا الشكل:

```lua
local WaypointsData = {
    ["1"] = {
        Vector3.new(100, 20, 50),
        Vector3.new(150, 25, 80)
    },

    ["1m"] = {
        Vector3.new(500, 30, 100),
        Vector3.new(600, 35, 150)
    }
}

return WaypointsData
```

كل اسم مثل `"1"` أو `"1m"` يعتبر قسم يحتوي على مجموعة إحداثيات.

## 🟢 استخدام الإحداثيات

تقدر تختار القسم:

```lua
local Waypoints = WaypointsData["1m"]
```

وتجيب إحداثية معينة:

```lua
local Position = Waypoints[1]
```

أو تمر على جميع الإحداثيات:

```lua
for _, Position in ipairs(Waypoints) do
    print(Position)
end
```

## 🔵 استخدام GitHub Raw

بدل وجود الإحداثيات داخل السكربت الأساسي، تقدر تخلي الملف على GitHub وتستدعيه عن طريق رابط Raw:

```lua
local WaypointsData = loadstring(game:HttpGet("RAW_URL"))()
```

بعدها تستخدم البيانات بشكل طبيعي:

```lua
local Position = WaypointsData["1m"][1]

print(Position)
```

## ⚡ مثال كامل

```lua
local WaypointsData = loadstring(game:HttpGet("RAW_URL"))()

local Waypoints = WaypointsData["1m"]

for _, Position in ipairs(Waypoints) do
    print(Position)
end
```

## 🌐 طريقة الحصول على Raw

افتح ملف `WaypointsData_GitHub.lua` في GitHub ثم اختر **Raw**.

استخدم رابط Raw داخل:

```lua
game:HttpGet("RAW_URL")
```

وهكذا يصير ملف الإحداثيات منفصل عن السكربت الأساسي وسهل تحديثه.

## 🇸🇦 English

**Waypoints Data** stores Roblox `Vector3` coordinates in organized sections.

You can use the coordinates directly or load the entire file from GitHub using a **Raw URL**.

```lua
local WaypointsData = loadstring(game:HttpGet("RAW_URL"))()
```

Then select a section:

```lua
local Position = WaypointsData["1m"][1]
```

And use the position inside your script.
