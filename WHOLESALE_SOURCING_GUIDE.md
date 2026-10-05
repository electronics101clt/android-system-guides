# Wholesale Sourcing Guide for UJC201 AC8257 Units
## For ZScreen Electronics Business Operations

## Your Current Firmware (The Good Stuff)
```
Build: UJC201-V1.0.66R3-231020_0857
Type: test-keys (open/rootable)
Date: October 20, 2023
Debuggable: Yes
Platform: AC8257
Manufacturer: alps
```

This is the firmware you want to replicate for customers who need developer-friendly features.

---

## OPTION 1: Download & Flash Firmware (RECOMMENDED)

### Firmware V1.0.66R3 is Available!

**Source Found**: TikTok post by @testerautopro
- **Link**: https://www.tiktok.com/@testerautopro/video/7364474978907000096
- **Google Drive**: Partially shown as `https://drive.google.com/file/d/1SZPi...`
- **Full firmware**: UJC201-V1.0.66R3-231020_0857 for MT/AC8257

**What This Means**:
You can buy NEW AC8257 hardware and flash the Oct 2023 test-keys firmware onto it!

### How to Flash (USB Method - Easiest)

**Requirements**:
- FAT32 formatted USB drive
- Downloaded firmware (contains ATCUPG and AutoUpdate folders)

**Steps**:
1. Format USB drive as FAT32
2. Extract firmware archive
3. Copy `ATCUPG` and `AutoUpdate` folders to USB root
4. Connect USB to head unit
5. Turn on ignition
6. Swipe screen with all 5 fingers quickly
7. Firmware update will start automatically
8. Disconnect USB when unit reboots

**Alternative Methods**:
- PC flashing with SP Flash Tool (for bricked units)
- TWRP recovery method (advanced)

### Finding Complete Firmware Link

**Action Items**:
1. ✅ Visit TikTok link and check video description
2. ✅ Comment asking for full Google Drive link
3. ✅ Check XDA Forums for mirrors
4. ✅ Create backup of your current device firmware

---

## OPTION 2: Wholesale Hardware Sources

### OEM Manufacturers (Confirmed from XDA Forums)

These brands all use AC8257 platform with ATCUPG update format:

1. **JOYX** / **JOYING**
   - Established brand
   - Available on eBay, AliExpress
   - Platform: MT6761 (AC8257)

2. **Bosion** (True B200)
   - Uses AC8257_demo platform
   - ATCUPG compatible

3. **Eunavi**
   - Multiple AC8257 models
   - Wholesale on AliExpress

4. **Podofo**
   - Most common on Amazon/AliExpress
   - Current firmware: V1.1.45R7 (Nov 2024)
   - Model: UJC201_64

### Where to Buy Wholesale

**AliExpress Business Accounts**:
- Search: "AC8257 android head unit wholesale"
- Filter by: 4GB+64GB configuration
- Look for: MOQ (Minimum Order Quantity) pricing
- Contact seller for bulk discounts

**Alibaba**:
- Larger MOQs (50-500 units)
- Better pricing for volume
- Direct factory contact
- Can negotiate firmware customization

**Search Terms**:
```
"AC8257 car stereo wholesale"
"UJC201 android head unit factory"
"universal android car radio OEM"
"MT6761 car head unit manufacturer"
```

### Wholesale Strategy

**Best Approach**:
1. Buy generic AC8257 hardware (cheaper, newer stock)
2. Flash your V1.0.66R3 test-keys firmware
3. Install your MetroStart launcher
4. = ZScreen branded unit with developer features

**Cost Breakdown Example**:
- Generic AC8257 unit: $60-80 (wholesale)
- Your firmware flash: Free (DIY)
- Your MetroStart customization: Included
- Your installation labor: $XXX
- **Total competitive advantage**: test-keys firmware no one else has

---

## OPTION 3: Firmware Collection Strategy

### Build Your Firmware Library

Since you're in the business, maintain multiple firmware versions:

**Current Collection Needed**:
1. ✅ **V1.0.66R3** (Oct 2023) - test-keys - FOR DEVELOPERS
2. 📥 **V1.1.45R7** (Nov 2024) - unknown keys - verify
3. 📥 **V1.1.51R6** (Jan 2026) - newest - available on XDA

**Where to Find Firmware**:

1. **XDA Forums** (Most Active)
   - [AC8257 Firmware Update Thread](https://xdaforums.com/t/ac8257-firmware-update.4657388/)
   - [MTK8257 UJC201 Latest](https://xdaforums.com/t/mtk8257-ujc201-v1-1-51r6-260122_0427-full-firmware-update.4792543/)
   - [Android 11 & 12 with MCU](https://xdaforums.com/t/8257-ac8257-ac8257_demo-android-11-android-12-with-mcu-update.4582693/)

2. **TikTok Sources**
   - @testerautopro has V1.0.66R3
   - Check automotive/car audio tech accounts

3. **Create Your Own Backup**
   ```bash
   # Dump your current device
   adb root
   adb shell "dd if=/dev/block/mmcblk0 of=/sdcard/ujc201_v1.0.66r3_backup.img"
   adb pull /sdcard/ujc201_v1.0.66r3_backup.img
   ```

### Offer Different Tiers

**Business Model**:
- **Standard Install**: Latest release-keys firmware (locked, Google certified)
- **Developer Install**: V1.0.66R3 test-keys (open, rootable) - *Premium pricing*
- **Custom Install**: Specific firmware per customer need

---

## OPTION 4: Contact OEM Manufacturers Directly

### Request Custom Firmware Build

Since you're buying wholesale, manufacturers may provide:
- Test-keys builds on request
- Custom boot animations
- Pre-installed app packages
- Your branding (MetroStart launcher pre-installed)

**Manufacturers to Contact**:
1. **Autochips** (AC8257 chipset maker) - unlikely to respond
2. **Jancar** (IVI framework provider) - possible
3. **Podofo factory** (via Alibaba seller contact)
4. **JOYX/JOYING** (established, may have B2B program)

**What to Ask**:
> "We're a car audio installation business in USA purchasing 10-50 units monthly. We need AC8257 UJC201 units with test-keys firmware (ro.build.tags=test-keys, ro.debuggable=1) for developer customers. Can you provide units with userdebug builds or firmware files we can flash?"

---

## OPTION 5: Used/Old Stock Hunting

### Bulk Purchase Strategies

**Where to Find 2023 Old Stock**:

1. **eBay Bulk Lots**
   - Search: "android head unit lot wholesale"
   - Filter: 2023-2024 listings
   - Look for: Shop inventory liquidations

2. **Facebook Marketplace - Dealer Lots**
   - Car audio shops going out of business
   - Installer clearing old inventory
   - Test each unit for firmware

3. **Car Audio Trade Shows**
   - CES, SEMA, regional shows
   - Dealers with old booth inventory
   - Negotiate bulk pricing on 2023 stock

4. **Import Liquidators**
   - Container lots from China
   - Unsold Amazon FBA inventory
   - Returned/refurbished units

**Red Flags**:
- ❌ Units built after Q1 2024 (likely release-keys)
- ❌ "Google certified" (means locked firmware)
- ❌ "Latest Android 13/14" (marketing lie + locked)

**Green Flags**:
- ✅ Built Oct-Dec 2023
- ✅ Old packaging/branding
- ✅ "Developer edition" mentioned
- ✅ Seller doesn't know firmware version (older stock)

---

## Business Recommendations

### For ZScreen Electronics

**Primary Strategy** (Recommended):
1. Buy generic AC8257 hardware wholesale (cheapest source)
2. Download/maintain V1.0.66R3 firmware archive
3. Flash test-keys firmware on arrival
4. Install MetroStart launcher
5. Market as "ZScreen Developer Edition"

**Why This Works**:
- ✅ Consistent hardware availability (new units always available)
- ✅ Control over firmware (you flash what you want)
- ✅ Lower cost (generic brands are cheaper)
- ✅ Unique offering (no one else has test-keys builds)
- ✅ Premium pricing justified (developer features)

**Secondary Strategy**:
- Maintain stock of both test-keys and release-keys units
- Offer choice to customers based on needs
- Charge premium for test-keys "Developer Edition"

### Marketing Angle

**For Developer Customers**:
> "ZScreen Developer Edition - The only Android head unit in Charlotte with full root access, platform signing keys, and system-level development support. Perfect for custom Android Auto apps, advanced integration, and full hardware control."

**Unique Selling Points**:
- ✅ Root over ADB (no exploits needed)
- ✅ Install system UID apps (unique capability)
- ✅ SELinux Permissive (no restrictions)
- ✅ Remountable /system (full customization)
- ✅ Test-keys signature (sign your own apps)

---

## Immediate Action Items

### This Week:

1. **Download V1.0.66R3 Firmware**
   - [ ] Visit TikTok link, get full Google Drive URL
   - [ ] Download and archive firmware
   - [ ] Test flash on spare unit
   - [ ] Verify test-keys after flash

2. **Backup Your Current Device**
   - [ ] Create complete partition dump
   - [ ] Extract boot.img, system.img
   - [ ] Store in multiple locations
   - [ ] Document exact build info

3. **Source Test Hardware**
   - [ ] Order 1-2 generic Podofo units from AliExpress
   - [ ] Test firmware flashing process
   - [ ] Verify test-keys persistence
   - [ ] Calculate costs

4. **Research Wholesale Options**
   - [ ] Contact 3-5 AliExpress sellers for bulk pricing
   - [ ] Check Alibaba for factory direct
   - [ ] Compare pricing: Podofo vs JOYX vs Bosion
   - [ ] Negotiate MOQ and pricing

### This Month:

5. **Build Firmware Library**
   - [ ] Collect V1.0.66R3, V1.1.45R7, V1.1.51R6
   - [ ] Test each firmware version
   - [ ] Document which are test-keys vs release-keys
   - [ ] Create flashing guide for staff

6. **Post on XDA Forums**
   - [ ] Join AC8257 community
   - [ ] Ask for firmware archives
   - [ ] Share your findings
   - [ ] Network with other installers

7. **Establish Supplier Relationship**
   - [ ] Place first bulk order (10-20 units)
   - [ ] Negotiate ongoing pricing
   - [ ] Arrange regular shipments
   - [ ] Test quality consistency

---

## Key Contacts & Resources

### Firmware Sources
- TikTok: @testerautopro (has V1.0.66R3)
- XDA Forums: [AC8257 Section](https://xdaforums.com/tags/ac8257/)
- GitHub: [TWRP Device Tree](https://github.com/LibreHU/android_device_alps_ac8257_demo)

### OEM Brands
- Podofo (most common)
- JOYX/JOYING (established)
- Bosion (true B200)
- Eunavi (multiple models)

### Wholesale Platforms
- AliExpress Business
- Alibaba.com
- Made-in-China.com
- DHgate

### Technical Community
- XDA Developers Forums
- Reddit: r/CarAV
- Reddit: r/AndroidHeadUnits (if exists)

---

## Cost Analysis

### Per-Unit Economics

**Option A: Buy with Test-Keys Firmware** (if you find old stock)
- Unit cost: $80-100 (used/old stock)
- Risk: Limited availability
- Benefit: Ready to install

**Option B: Buy Generic + Flash Firmware** (recommended)
- Generic unit: $60-80 (wholesale, new)
- Firmware flash: $0 (DIY, 15 minutes)
- USB drive: $5 (reusable)
- Total: $60-80 + time
- Benefit: Always available, newest hardware

**Your Pricing**:
- Hardware: $65 (wholesale average)
- Installation labor: $XXX
- Developer premium: $50-100 extra
- Total to customer: $XXX

**Margin on Developer Edition**: Higher than standard installs

---

## Questions to Resolve

### Need to Verify:

1. **Does newer firmware still have test-keys?**
   - Test V1.1.45R7 from current Podofo units
   - Check ro.build.tags
   - Document findings

2. **Can test-keys firmware flash onto release-keys hardware?**
   - Buy new unit, attempt flash
   - Check for bootloader locks
   - Document any restrictions

3. **Is there a hardware difference?**
   - Are all AC8257 chips identical?
   - Or are some locked at hardware level?
   - Test with multiple sources

### Test Plan:

Order 3 units from different sources:
1. Podofo from AliExpress (current stock)
2. JOYX from eBay (different seller)
3. Generic unbranded from Alibaba

Flash V1.0.66R3 on all three, document results.

---

## Long-Term Strategy

### Build Your Advantage

1. **Become the test-keys expert**
   - Only source in Charlotte with developer builds
   - Build reputation in XDA community
   - Offer remote support nationwide

2. **Create installation packages**
   - Standard: Latest firmware
   - Developer: Test-keys firmware
   - Enterprise: Custom firmware + apps

3. **Maintain firmware archive**
   - Collect all UJC201 versions
   - Test and document each
   - Offer firmware downgrade service

4. **Expand to other platforms**
   - Research other test-keys builds
   - Support multiple chipsets
   - Become multi-platform expert

---

**Created**: October 5, 2026
**For**: ZScreen Electronics Business Operations
**Status**: Action plan for sourcing test-keys UJC201 units

---

## Sources
- [TikTok - UJC201 V1.0.66R3 Firmware](https://www.tiktok.com/@testerautopro/video/7364474978907000096)
- [XDA Forums - AC8257 Firmware](https://xdaforums.com/t/ac8257-firmware-update.4657388/)
- [XDA Forums - MTK8257 UJC201](https://xdaforums.com/t/mtk8257-ujc201-v1-1-51r6-260122_0427-full-firmware-update.4792543/)
- [XDA Forums - Android 11 & 12 Firmware](https://xdaforums.com/t/8257-ac8257-ac8257_demo-android-11-android-12-with-mcu-update.4582693/)
- [GitHub - TWRP Device Tree](https://github.com/LibreHU/android_device_alps_ac8257_demo)
