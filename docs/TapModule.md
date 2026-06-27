# 🎯 TapModule - Complete Setup Guide

**TapModule** is an advanced PvP module for the Minecraft mod Raven that automatically performs various types of "tap" mechanics (W-Tap, S-Tap, A-Tap, D-Tap) to improve PvP performance.

---

## 📋 **Basic Information**

- **Category**: Combat
- **Description**: Advanced tap mechanics for PvP
- **Activation**: Left mouse button (attack)
- **Goal**: Automatic improvement of PvP skills

---

## 🎮 **Available tap modes**

### **1. W-Tap** 
- **Description**: Classic W-Tap for aggressive PvP
- **Purpose**: Increase knockback effect
- **When to use**: Aggressive attacks, close PvP
- **Uses settings**: Tap Delay, Release Time, Chance, Range, Enable W-Tap

### **2. S-Tap**
- **Description**: Defensive S-Tap for retreat
- **Purpose**: Reduce knockback effect
- **When to use**: Defensive PvP, retreat, low health
- **Uses settings**: Tap Delay, Release Time, Chance, Range, Enable S-Tap

### **3. A-Tap**
- **Description**: Left strafe tap
- **Purpose**: Leftward side movement
- **When to use**: Strafe PvP, dodging attacks
- **Uses settings**: Tap Delay, Release Time, Chance, Range, Enable A-Tap

### **4. D-Tap**
- **Description**: Right strafe tap
- **Purpose**: Rightward side movement
- **When to use**: Strafe PvP, dodging attacks
- **Uses settings**: Tap Delay, Release Time, Chance, Range, Enable D-Tap

### **5. SmartTap**
- **Description**: Intelligent selection based on situation with fixed logic
- **Purpose**: Automatic selection of best tap based on distance and CPS
- **When to use**: Advanced PvP, automatic decision making
- **Uses settings**: ALL settings + Aggressive Range, Defensive Range
- **How it works**: 
  - **Aggressive**: W-Tap when distance ≤ Aggressive Range and CPS ≥ 8
  - **Defensive**: S-Tap when distance > Defensive Range or health < 6.0
  - **Strafe**: A-Tap or D-Tap when distance 2.5-4.0 blocks (randomly)
  - **Default**: W-Tap for other situations

### **6. AdaptiveTap**
- **Description**: Adaptive tapping based on CPS with fixed multipliers
- **Purpose**: Adaptation to your clicking speed
- **When to use**: Dynamic PvP, various speeds
- **Uses settings**: ALL settings + Min CPS, Max CPS, Adaptive Multiplier
- **How it works**: 
  - **Slow CPS** (< Min CPS): Multiplier × 1.5 (slower tapping)
  - **Normal CPS** (Min-Max): Uses base multiplier
  - **Fast CPS** (> Max CPS): Multiplier × 0.7 (faster tapping)

### **7. ComboTap**
- **Description**: Combination of multiple taps with simplified logic
- **Purpose**: Combination of forward and strafe movements
- **When to use**: Complex movement patterns
- **Uses settings**: ALL settings + all Enable settings
- **How it works**: 
  - **Forward**: If W-Tap OR S-Tap is enabled → stops forward movement
  - **Strafe**: If A-Tap OR D-Tap is enabled → stops strafe movement

---

## 📊 **Overview - Which settings are used for each mode**

| Mode | Basic Settings | Enable Settings | Smart Settings | Adaptive Settings |
|------|----------------|-----------------|----------------|-------------------|
| **W-Tap** | ✅ All | ✅ Enable W-Tap | ❌ | ❌ |
| **S-Tap** | ✅ All | ✅ Enable S-Tap | ❌ | ❌ |
| **A-Tap** | ✅ All | ✅ Enable A-Tap | ❌ | ❌ |
| **D-Tap** | ✅ All | ✅ Enable D-Tap | ❌ | ❌ |
| **SmartTap** | ✅ All | ✅ All Enable | ✅ Aggressive/Defensive Range | ❌ |
| **AdaptiveTap** | ✅ All | ✅ All Enable | ✅ Aggressive/Defensive Range | ✅ Min/Max CPS, Multiplier |
| **ComboTap** | ✅ All | ✅ All Enable | ✅ Aggressive/Defensive Range | ✅ Min/Max CPS, Multiplier |

### **Legend:**
- ✅ **Basic Settings**: Tap Delay, Release Time, Chance, Range, Only Players
- ✅ **Enable Settings**: Enable W-Tap, S-Tap, A-Tap, D-Tap
- ✅ **Smart Settings**: Aggressive Range, Defensive Range
- ✅ **Adaptive Settings**: Min CPS, Max CPS, Adaptive Multiplier

---

## ⚙️ **Detailed Settings**

> **💡 IMPORTANT:** All settings are always used, but their significance varies depending on the selected mode. For example, in W-Tap mode, Adaptive settings are ignored, but in AdaptiveTap mode, all settings are used.

### **🎯 Basic Settings**

#### **Tap Mode**
- **Type**: ModeSetting
- **Options**: W-Tap, S-Tap, A-Tap, D-Tap, SmartTap, AdaptiveTap, ComboTap
- **Default**: W-Tap
- **Description**: Selects the basic tap type

#### **Tap Delay (ms)** - 10-200ms
- **Type**: SliderSetting
- **Range**: 10ms - 200ms
- **Step**: 5ms
- **Default**: 50ms
- **What it does**: Time between releasing and restoring movement
- **Recommended values**:
  - **10-30ms**: Fast, aggressive tapping
  - **50-80ms**: Balanced tapping (recommended)
  - **100-200ms**: Slow, defensive tapping

#### **Release Time (ms)** - 5-100ms
- **Type**: SliderSetting
- **Range**: 5ms - 100ms
- **Step**: 5ms
- **Default**: 25ms
- **What it does**: How long to keep the key released
- **Recommended values**:
  - **5-15ms**: Minimal release
  - **25-40ms**: Standard release (recommended)
  - **50-100ms**: Long release for stronger effects

#### **Chance %** - 0-100%
- **Type**: SliderSetting
- **Range**: 0% - 100%
- **Step**: 5%
- **Default**: 100%
- **What it does**: Probability of triggering the tap
- **Recommended values**:
  - **100%**: Always trigger tap
  - **80-90%**: Mostly trigger tap
  - **50-70%**: Random triggering

#### **Range** - 1.0-6.0 blocks
- **Type**: SliderSetting
- **Range**: 1.0 - 6.0 blocks
- **Step**: 0.1 block
- **Default**: 4.0 blocks
- **What it does**: Maximum distance for activation
- **Recommended values**:
  - **1.0-2.0**: Only at close contact
  - **3.0-4.0**: Standard PvP distance (recommended)
  - **5.0-6.0**: Long distance

---

### **🔧 Advanced Settings**

> **📝 Note:** These settings affect module behavior but are not specific to individual modes. They always work when enabled.

#### **Only Players** ✅
- **Type**: ButtonSetting
- **Default**: Enabled
- **What it does**: Activates tap only on players, not on mobs
- **Recommended**: ✅ Enabled for PvP

#### **Smart Mode** ✅
- **Type**: ButtonSetting
- **Default**: Disabled
- **What it does**: **WARNING: This setting is DEPRECATED!** Smart Mode is now a separate SmartTap mode
- **Recommended**: ❌ Don't use - instead use "SmartTap" mode

#### **Adaptive Mode** ✅
- **Type**: ButtonSetting
- **Default**: Disabled
- **What it does**: **WARNING: This setting is DEPRECATED!** Adaptive Mode is now a separate AdaptiveTap mode
- **Recommended**: ❌ Don't use - instead use "AdaptiveTap" mode

---

### **⌨️ Individual tap settings**

> **📝 Note:** These settings determine which taps are enabled. For W-Tap mode, only Enable W-Tap is needed, for Smart/Adaptive/Combo modes enable all necessary taps.

#### **Enable W-Tap** ✅
- **Type**: ButtonSetting
- **Default**: Enabled
- **What it does**: Enables W-Tap mechanics
- **When to use**: Aggressive PvP, knockback

#### **Enable S-Tap** ✅
- **Type**: ButtonSetting
- **Default**: Disabled
- **What it does**: Enables S-Tap mechanics  
- **When to use**: Defensive PvP, retreat

#### **Enable A-Tap** ✅
- **Type**: ButtonSetting
- **Default**: Disabled
- **What it does**: Enables left strafe tap
- **When to use**: Side movement, strafe PvP

#### **Enable D-Tap** ✅
- **Type**: ButtonSetting
- **Default**: Disabled
- **What it does**: Enables right strafe tap
- **When to use**: Side movement, strafe PvP

---

### **🎮 Smart Mode settings**

> **📝 Note:** These settings are used ONLY in SmartTap, AdaptiveTap or ComboTap modes. For W-Tap, S-Tap, A-Tap, D-Tap modes they are ignored.

#### **Aggressive Range** - 1.0-4.0 blocks
- **Type**: SliderSetting
- **Range**: 1.0 - 4.0 blocks
- **Step**: 0.1 block
- **Default**: 2.5 blocks
- **What it does**: Distance for aggressive W-Tap in SmartTap mode
- **Recommended values**:
  - **1.0-2.0**: Very aggressive
  - **2.5-3.0**: Balanced (recommended)
  - **3.5-4.0**: Less aggressive

#### **Defensive Range** - 2.0-6.0 blocks
- **Type**: SliderSetting
- **Range**: 2.0 - 6.0 blocks
- **Step**: 0.1 block
- **Default**: 4.0 blocks
- **What it does**: Distance for defensive S-Tap in SmartTap mode
- **Recommended values**:
  - **2.0-3.0**: Early defense
  - **4.0-5.0**: Standard defense (recommended)
  - **5.5-6.0**: Late defense

---

### **⚡ Adaptive Mode settings**

> **📝 Note:** These settings are used ONLY in AdaptiveTap or ComboTap modes. For W-Tap, S-Tap, A-Tap, D-Tap or SmartTap modes they are ignored.

#### **Adaptive Min CPS** - 1-15 CPS
- **Type**: SliderSetting
- **Range**: 1 - 15 CPS
- **Step**: 1 CPS
- **Default**: 6 CPS
- **What it does**: Minimum CPS for increasing multiplier (×1.5)
- **Recommended values**:
  - **1-5**: For slow players
  - **6-8**: Standard (recommended)
  - **9-15**: For fast players

#### **Adaptive Max CPS** - 8-20 CPS
- **Type**: SliderSetting
- **Range**: 8 - 20 CPS
- **Step**: 1 CPS
- **Default**: 12 CPS
- **What it does**: Maximum CPS for decreasing multiplier (×0.7)
- **Recommended values**:
  - **8-12**: Standard (recommended)
  - **13-16**: For fast players
  - **17-20**: For very fast players

#### **Adaptive Multiplier** - 0.5-2.0x
- **Type**: SliderSetting
- **Range**: 0.5x - 2.0x
- **Step**: 0.1x
- **Default**: 1.0x
- **What it does**: Base multiplier for timing
- **Recommended values**:
  - **0.5-0.8**: Slow tapping
  - **1.0**: Standard (recommended)
  - **1.5-2.0**: Fast tapping

---

### **🐛 Debug settings**

#### **Debug Mode** ✅
- **Type**: ButtonSetting
- **Default**: Disabled
- **What it does**: Shows tap information in chat
- **Messages**:
  - `§6[TapModule] §aEnabled - [TapType]` - Module enabled
  - `§6[TapModule] §fStarting tap: [TapType]` - Tap starting
  - `§6[TapModule] §fCompleted [TapType] tap` - Tap completed

---

## 🎯 **Recommended configurations**

### **🚀 For beginners:**
```
Tap Mode: W-Tap
Tap Delay: 60ms
Release Time: 30ms
Chance: 100%
Range: 4.0
Smart Mode: ❌ (DEPRECATED)
Adaptive Mode: ❌ (DEPRECATED)
Enable W-Tap: ✅
Enable S-Tap: ❌
Enable A-Tap: ❌
Enable D-Tap: ❌
Debug Mode: ❌
```

### **⚔️ For advanced users:**
```
Tap Mode: SmartTap
Tap Delay: 50ms
Release Time: 25ms
Chance: 90%
Range: 4.5
Smart Mode: ❌ (DEPRECATED)
Adaptive Mode: ❌ (DEPRECATED)
Aggressive Range: 2.5
Defensive Range: 4.0
Enable W-Tap: ✅
Enable S-Tap: ✅
Enable A-Tap: ✅
Enable D-Tap: ✅
Debug Mode: ❌
```

### **🔥 For experts:**
```
Tap Mode: AdaptiveTap
Tap Delay: 40ms
Release Time: 20ms
Chance: 85%
Range: 5.0
Smart Mode: ❌ (DEPRECATED)
Adaptive Mode: ❌ (DEPRECATED)
Aggressive Range: 2.0
Defensive Range: 3.5
Min CPS: 8
Max CPS: 15
Adaptive Multiplier: 1.2
Enable W-Tap: ✅
Enable S-Tap: ✅
Enable A-Tap: ✅
Enable D-Tap: ✅
Debug Mode: ✅
```

---

## ⚠️ **Important notes**

1. **Tap only works while holding left mouse button** (attack)
2. **Module ignores bots** thanks to AntiBot integration
3. **Smart Mode and Adaptive Mode settings are DEPRECATED** - instead use corresponding modes
4. **SmartTap mode** has fixed logic with hardcoded values (CPS ≥ 8, distance 2.5-4.0)
5. **AdaptiveTap mode** has fixed multipliers (×1.5 for slow CPS, ×0.7 for fast CPS)
6. **ComboTap mode** has simplified logic - only combines forward and strafe
7. **Debug Mode** is useful for tuning settings

---

## 🔄 **How it works - Technical description**

### **1. Target detection**
```java
private Entity getTarget() {
    if (mc.objectMouseOver != null)
        return mc.objectMouseOver.entityHit; 
    return null;
}
```

### **2. Condition checking**
```java
private boolean shouldExecuteTap() {
    if (!Mouse.isButtonDown(0)) return false;           // Left mouse button
    if (mc.currentScreen != null) return false;         // Not in GUI
    Entity target = getTarget();
    if (target == null) return false;                   // Has target
    if (Config.onlyPlayers.isToggled() && !(target instanceof EntityPlayer)) return false; // Only players
    if (AntiBot.isBot(target)) return false;            // Not a bot
    if (mc.thePlayer.getDistanceToEntity(target) > Config.range.getInput()) return false; // Distance
    return (Math.random() * 100.0D <= Config.chance.getInput()); // Chance
}
```

### **3. SmartTap logic (fixed)**
```java
private TapMode getSmartTap(Entity target) {
    double dist = mc.thePlayer.getDistanceToEntity(target);
    int cps = CPSCalculator.f();
    
    if (dist <= Config.aggressiveRange.getInput() && cps >= 8)
        return TapMode.W_TAP;                           // Aggressive (hardcoded CPS ≥ 8)
    if (dist > Config.defensiveRange.getInput() || mc.thePlayer.getHealth() < 6.0F)
        return TapMode.S_TAP;                           // Defensive (hardcoded health < 6.0)
    if (dist > 2.5D && dist <= 4.0D)                   // Hardcoded distance
        return ThreadLocalRandom.current().nextBoolean() ? TapMode.A_TAP : TapMode.D_TAP; // Strafe
    return TapMode.W_TAP;                               // Default
}
```

### **4. Adaptive timing (fixed multipliers)**
```java
private void updateAdaptive() {
    long now = System.currentTimeMillis();
    if (now - this.lastCPSCheck < 1000L) return;
    
    int cps = CPSCalculator.f();
    double multiplier = Config.adaptiveMultiplier.getInput();
    
    this.adaptiveMultiplier = (cps < Config.minCPS.getInput()) ? 
        (multiplier * 1.5D) :                           // Fixed multiplier 1.5
        ((cps > Config.maxCPS.getInput()) ? 
            (multiplier * 0.7D) : multiplier);          // Fixed multiplier 0.7
    
    this.lastCPSCheck = now;
}
```

### **5. ComboTap logic (simplified)**
```java
case COMBO:
    if (Config.wTap.isToggled() || Config.sTap.isToggled())
        event.setForward(0.0F);                         // Combines forward
    if (Config.aTap.isToggled() || Config.dTap.isToggled())
        event.setStrafe(0.0F);                          // Combines strafe
    return;
```

---

## 🎮 **Practical tips**

### **For different PvP types:**

#### **BedWars:**
- **Tap Mode**: SmartTap
- **Range**: 4.5-5.0
- **Chance**: 90-95%

#### **SkyWars:**
- **Tap Mode**: AdaptiveTap
- **Range**: 4.0-4.5
- **Chance**: 85-90%

#### **Duels:**
- **Tap Mode**: ComboTap
- **Range**: 3.5-4.0
- **Chance**: 100%

#### **FFA:**
- **Tap Mode**: SmartTap
- **Range**: 5.0-6.0
- **Chance**: 80-85%

---

## 🔧 **Troubleshooting**

### **Tap doesn't trigger:**
1. Check if you're holding left mouse button
2. Check distance to target
3. Check Chance % setting
4. Check if target is a player (Only Players)

### **Tap is too fast/slow:**
1. Adjust Tap Delay
2. Adjust Release Time
3. Use AdaptiveTap mode
4. Adjust Adaptive Multiplier

### **SmartTap doesn't work properly:**
1. Check Aggressive Range
2. Check Defensive Range
3. Enable all necessary taps
4. **Warning**: SmartTap has hardcoded values (CPS ≥ 8, distance 2.5-4.0)

### **AdaptiveTap doesn't work properly:**
1. Check Min CPS and Max CPS
2. Adjust Adaptive Multiplier
3. **Warning**: AdaptiveTap has fixed multipliers (×1.5, ×0.7)

---

## 📊 **Performance metrics**

### **Optimal values for different CPS:**

| Your CPS | Tap Delay | Release Time | Multiplier |
|----------|-----------|--------------|------------|
| 1-5      | 80-100ms  | 40-50ms      | 0.8-1.0   |
| 6-10     | 50-70ms   | 25-35ms      | 1.0-1.2   |
| 11-15    | 30-50ms   | 15-25ms      | 1.2-1.5   |
| 16+      | 20-40ms   | 10-20ms      | 1.5-2.0   |

---

## 🎯 **Conclusion**

TapModule is a powerful tool for improving PvP skills. The key to success is:

1. **Start with simple settings** (W-Tap, basic timing)
2. **Gradually add advanced features** (SmartTap, AdaptiveTap modes)
3. **Tune settings according to your play style**
4. **Use Debug Mode** for optimization
5. **Test in various PvP situations**
6. **Remember limitations** of SmartTap and AdaptiveTap modes

With proper settings, you'll become a much more effective PvP player!

---

## 🎯 **Practical configuration examples**

### **Scenario 1: You want only W-Tap**
```
Tap Mode: W-Tap
Enable W-Tap: ✅
Enable S-Tap: ❌ (ignored)
Enable A-Tap: ❌ (ignored)
Enable D-Tap: ❌ (ignored)
Smart Mode: ❌ (DEPRECATED - ignored)
Adaptive Mode: ❌ (DEPRECATED - ignored)
```
**Result**: Module performs only W-Tap with your basic settings.

### **Scenario 2: You want SmartTap mode**
```
Tap Mode: SmartTap
Enable W-Tap: ✅ (used for aggressive PvP)
Enable S-Tap: ✅ (used for defensive PvP)
Enable A-Tap: ✅ (used for strafe)
Enable D-Tap: ✅ (used for strafe)
Smart Mode: ❌ (DEPRECATED - ignored)
Adaptive Mode: ❌ (DEPRECATED - ignored)
Aggressive Range: 2.5 (used)
Defensive Range: 4.0 (used)
```
**Result**: Module automatically selects the best tap according to fixed logic (CPS ≥ 8, distance 2.5-4.0).

### **Scenario 3: You want fully adaptive system**
```
Tap Mode: AdaptiveTap
Enable W-Tap: ✅
Enable S-Tap: ✅
Enable A-Tap: ✅
Enable D-Tap: ✅
Smart Mode: ❌ (DEPRECATED - ignored)
Adaptive Mode: ❌ (DEPRECATED - ignored)
Aggressive Range: 2.0
Defensive Range: 3.5
Min CPS: 8
Max CPS: 15
Adaptive Multiplier: 1.2
```
**Result**: Module automatically selects tap and adapts timing according to your CPS with fixed multipliers (×1.5, ×0.7).

---

## ❓ **Frequently Asked Questions**

### **Question: Do I need to enable all Enable settings for W-Tap mode?**
**Answer**: No! For W-Tap mode, you only need to enable "Enable W-Tap". Other Enable settings are ignored.

### **Question: Why don't Adaptive settings work in W-Tap mode?**
**Answer**: Adaptive settings are only used in AdaptiveTap or ComboTap modes. W-Tap mode uses only basic settings.

### **Question: How does SmartTap work with different Enable settings?**
**Answer**: SmartTap automatically selects between enabled taps according to fixed logic. If you only enable W-Tap and S-Tap, SmartTap will only choose between these two.

### **Question: Why are Smart Mode and Adaptive Mode settings marked as DEPRECATED?**
**Answer**: These settings are outdated and don't work. Instead, use corresponding modes: SmartTap and AdaptiveTap.

### **Question: What are the hardcoded values in SmartTap mode?**
**Answer**: 
- **CPS threshold**: ≥ 8 for aggressive W-Tap
- **Distance for strafe**: 2.5-4.0 blocks
- **Health threshold**: < 6.0 for defensive S-Tap

### **Question: What are the fixed multipliers in AdaptiveTap mode?**
**Answer**: 
- **Slow CPS** (< Min CPS): ×1.5
- **Fast CPS** (> Max CPS): ×0.7
- **Normal CPS**: Uses base multiplier

---

*This guide was created for the Minecraft mod Raven with TapModule. All information is based on actual implementation in the code.*
