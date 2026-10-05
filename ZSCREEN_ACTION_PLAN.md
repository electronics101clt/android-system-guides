# ZScreen Action Plan - Test-Keys Unit Sourcing
## October 5, 2026

## 🎯 THE SOLUTION FOUND

**You can buy NEW hardware and flash your OLD firmware!**

### The Game-Changer:
- Generic AC8257 units: $60-80 wholesale (always available)
- Your V1.0.66R3 firmware: **Available for download** ✅
- Flash process: 15 minutes per unit
- Result: Test-keys developer units at low cost

---

## 📥 STEP 1: GET THE FIRMWARE (DO TODAY)

### Firmware V1.0.66R3 is on Google Drive!

**Source**: TikTok @testerautopro
🔗 https://www.tiktok.com/@testerautopro/video/7364474978907000096

**Action**:
1. Open TikTok link
2. Look for full Google Drive URL (shown as "https://drive.google.com/file/d/1SZPi...")
3. Download complete firmware archive
4. Save to: `/backup/firmware/UJC201-V1.0.66R3-231020_0857/`

**Backup Plan**:
- Comment on TikTok asking for link
- Check XDA Forums for mirrors
- Create dump from your existing device (see below)

### Backup Your Current Device (Insurance):
```bash
# Connect your MetroStart unit via ADB
adb root
adb shell "dd if=/dev/block/mmcblk0 of=/sdcard/ujc201_backup.img bs=4M"
adb pull /sdcard/ujc201_backup.img ./firmware_backup/

# This creates a complete backup you can flash to new units
```

---

## 🛒 STEP 2: ORDER TEST HARDWARE (DO THIS WEEK)

### Buy 2-3 Generic Units to Test

**Recommended Source**: AliExpress Podofo
- Search: "Podofo AC8257 android head unit 4GB 64GB"
- Price range: $70-90 shipped
- Ship time: 2-3 weeks

**Alternative**: Amazon Prime (faster testing)
- Search: "10.1 universal android car stereo 4+64"
- Higher price but 2-day shipping
- Can test flashing process immediately

**What to Buy**:
- Model: ANY AC8257 / UJC201 variant
- Specs: 4GB+64GB minimum (6GB+128GB also works)
- Don't worry about firmware version (you'll flash yours)

---

## 🔧 STEP 3: TEST FLASH PROCESS (WHEN UNITS ARRIVE)

### Flash Method (USB - Easiest):

**Requirements**:
- FAT32 USB drive (any size)
- Downloaded V1.0.66R3 firmware
- New test unit

**Steps**:
1. Format USB as FAT32
2. Extract firmware (contains `ATCUPG` and `AutoUpdate` folders)
3. Copy both folders to USB root
4. Connect USB to head unit
5. Power on unit
6. **Swipe with all 5 fingers** on screen quickly
7. Flashing begins automatically
8. Wait for reboot
9. Disconnect USB

### Verify Test-Keys After Flash:
```bash
adb devices
adb shell getprop ro.build.tags           # Must show: test-keys
adb shell getprop ro.debuggable           # Must show: 1
adb shell getprop ro.build.display.id     # Should show: UJC201-V1.0.66R3-231020_0857
adb root                                   # Should succeed
```

**If all checks pass = SUCCESS!**
You can now flash any AC8257 unit with test-keys firmware.

---

## 💼 STEP 4: ESTABLISH WHOLESALE SOURCE (THIS MONTH)

### Once Flash Process is Verified:

**Contact AliExpress Sellers**:
```
Subject: Bulk Order Inquiry - AC8257 Android Head Units

Hello,

I operate a car audio installation business in USA (ZScreen Electronics,
Charlotte NC). We install 10-50 Android head units monthly.

I'm interested in:
- AC8257 / UJC201 units (4GB+64GB or 6GB+128GB)
- Monthly order: 10-20 units to start
- Shipping to Charlotte, NC, USA

Questions:
1. What is your MOQ (minimum order quantity)?
2. What is your bulk pricing for 10, 20, 50 units?
3. What is your best price per unit?
4. Do you provide firmware files?
5. What is typical shipping time to USA?

Please provide your best wholesale pricing.

Thank you,
ZScreen Electronics
```

**Send to 5-10 sellers**, compare responses.

### Expected Wholesale Pricing:
- 1 unit: $80-90
- 10 units: $65-75 each
- 50 units: $55-65 each
- 100+ units: $50-60 each

---

## 📊 BUSINESS MODEL

### Two-Tier Offering:

**Standard Install** - $XXX
- Latest firmware (release-keys)
- Google certified
- Locked/secure
- For regular customers

**Developer Edition** - $XXX + $75-100 premium
- V1.0.66R3 test-keys firmware
- Root access
- Platform signing
- System development
- ZScreen MetroStart launcher
- **Unique in Charlotte market**

### Cost Breakdown (Developer Edition):
- Hardware (wholesale): $65
- Firmware flash: $0 (15 min labor)
- MetroStart install: Included
- Installation labor: $XXX
- **Developer premium**: $75-100
- **Total to customer**: $XXX
- **Your margin**: Better than standard

---

## 🎯 COMPETITIVE ADVANTAGE

### What You'll Have That Others Don't:

1. **Only test-keys source in Charlotte**
   - No other installer has this
   - Can't buy these retail anymore
   - You control the firmware

2. **Developer customer base**
   - Android developers
   - Custom integration projects
   - Advanced car audio enthusiasts
   - System-level app developers

3. **Premium pricing justified**
   - Unique capability
   - Real technical value
   - No competition

4. **Scalable process**
   - Flash firmware once = reusable
   - Can train staff
   - Consistent quality

---

## 📅 30-DAY TIMELINE

### Week 1 (Now):
- ✅ Download V1.0.66R3 firmware
- ✅ Backup current device
- ✅ Order 2-3 test units from AliExpress/Amazon

### Week 2-3:
- ✅ Test flash process
- ✅ Verify test-keys persistence
- ✅ Document process for staff
- ✅ Calculate true costs

### Week 3-4:
- ✅ Contact 5-10 wholesale sellers
- ✅ Compare pricing
- ✅ Negotiate terms
- ✅ Place first bulk order (10-20 units)

### Week 4+:
- ✅ Receive bulk order
- ✅ Flash all units with V1.0.66R3
- ✅ Install MetroStart launcher
- ✅ Market "Developer Edition"
- ✅ Establish recurring orders

---

## ⚠️ CRITICAL QUESTIONS TO ANSWER

### During Testing Phase:

1. **Does flash work on all AC8257 variants?**
   - Test Podofo, JOYX, generic brands
   - Document any incompatibilities

2. **Does test-keys persist after flash?**
   - Verify ro.build.tags stays "test-keys"
   - Check if any units revert to release-keys

3. **Are there bootloader locks?**
   - Some units may have locked bootloaders
   - Test different batches/sellers

4. **What's the failure rate?**
   - Document any bricked units
   - Establish recovery process

---

## 🆘 BACKUP PLANS

### If Firmware Download Fails:

**Plan B**: Extract from your current device
```bash
adb root
adb pull /system/build.prop
# Extract full system partition
# Create flashable zip
```

**Plan C**: XDA Forums community
- Post asking for V1.0.66R3 archive
- Offer to trade/share findings
- Someone likely has it saved

### If Flash Process Doesn't Work:

**Plan B**: PC Flashing (SP Flash Tool)
- More complex but more reliable
- Can flash bricked units
- Requires Windows PC

**Plan C**: TWRP Recovery method
- Install TWRP first
- Flash firmware as OTA
- More control over process

---

## 📞 RESOURCES

### Firmware Sources:
- **TikTok**: @testerautopro (has V1.0.66R3)
- **XDA Forums**: https://xdaforums.com/tags/ac8257/
- **GitHub**: https://github.com/LibreHU/android_device_alps_ac8257_demo

### Wholesale Sources:
- **AliExpress**: Search "AC8257 wholesale"
- **Alibaba**: Search "UJC201 factory"
- **Made-in-China**: Search "android car radio OEM"

### Technical Community:
- **XDA AC8257 Forums**: Ask questions, share findings
- **Reddit r/CarAV**: Market research
- **Your existing customers**: Beta testers for Developer Edition

---

## 💡 QUICK WINS

### Things You Can Do Right Now:

1. **Message @testerautopro on TikTok**
   - "Hi, I run a car audio shop in Charlotte. Need the full Google Drive link for UJC201-V1.0.66R3 firmware. Thanks!"

2. **Post on XDA Forums**
   - "Looking for UJC201 V1.0.66R3 firmware archive for business use. Can anyone share?"

3. **Order 2 test units on Amazon**
   - Get them in 2 days
   - Test flash this weekend
   - Verify process works

4. **Create firmware backup from current device**
   - Insurance policy
   - Can share with community
   - Establish yourself as source

---

## 🎉 THE BOTTOM LINE

### You Have Everything You Need:

✅ **Firmware is available** (TikTok/XDA)
✅ **Hardware is available** (wholesale, new, cheap)
✅ **Flash process is known** (USB method, 15 minutes)
✅ **Market exists** (developers need test-keys)
✅ **No competition** (you're the only source locally)

### Next Action:
**Download that firmware TODAY** before it disappears!

---

**Created**: October 5, 2026
**For**: ZScreen Electronics (Charlotte, NC)
**Phone**: (980) 272-0017
**Goal**: Establish reliable source of test-keys UJC201 units

**All documentation**: https://github.com/electronics101clt/android-system-guides
