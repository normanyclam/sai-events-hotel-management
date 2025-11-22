# Hotel Booking Manager

A web-based hotel room booking management platform with inventory tracking, customer management, and comprehensive reporting. All data is stored locally in your browser - no server required.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)

## 🌟 Features

- **Hotel Management** - Add and manage multiple hotels with contact information
- **Room Type Configuration** - Define room types with nightly rates per hotel
- **Customer Database** - Store customer information with contact details
- **Smart Booking System** - Automatic night calculation, rate lookup, and inventory deduction
- **Room Inventory Tracking** - 30-day visual overview with color-coded availability
- **Reconciliation Dashboard** - Monitor occupancy rates and identify dates needing attention
- **Import/Export** - Bulk CSV imports and Excel export with multiple sheets
- **Local Persistence** - All data saved in browser localStorage
- **Offline Capable** - Works without internet connection
- **Zero Setup** - No installation or configuration required

## 🚀 Quick Start

### Option 1: Use GitHub Pages (Recommended)

1. Visit the live app: `https://yourusername.github.io/hotel-booking-manager`
2. Start using immediately - no installation needed
3. Bookmark for quick access

### Option 2: Run Locally

1. Download `index.html`
2. Open the file in any modern browser
3. Start managing your bookings

## 📋 Table of Contents

- [Getting Started](#getting-started)
- [Core Workflows](#core-workflows)
- [Import & Export](#import--export)
- [Backup & Restore](#backup--restore)
- [Troubleshooting](#troubleshooting)
- [Best Practices](#best-practices)
- [License](#license)

## 🏁 Getting Started

### Step 1: Add Hotels

1. Click the **Hotels** tab
2. Fill in hotel information:
   - Hotel Name (required)
   - Location
   - Contact information
3. Click **Add Hotel**

### Step 2: Configure Room Types

Each hotel needs room types with pricing:

1. Scroll to "Room Types" section in **Hotels** tab
2. Enter:
   - Room Type Name (e.g., "Deluxe Suite")
   - Nightly Rate (price per night)
   - Select the Hotel
3. Click **Add Room Type**

**Example:**
```
Grand Hyatt
├── Deluxe Room - $250/night
├── Executive Suite - $450/night
└── Presidential Suite - $800/night
```

### Step 3: Add Customers

1. Click the **Customers** tab
2. Enter customer details (Name, Email, Phone)
3. Click **Add Customer**

### Step 4: Set Room Inventory

Allocate available rooms before accepting bookings:

1. Click **Room Inventory** tab
2. Select Hotel, Room Type, Date
3. Enter Total Rooms Available
4. Click **Set Inventory** or **Set for Date Range**

**Example:** Allocate 50 rooms at Grand Hyatt for Feb 4-6:
```
Hotel: Grand Hyatt
Room Type: Deluxe Room
Total Rooms: 50
Date Range: 2025-02-04 to 2025-02-06
```

### Step 5: Create Bookings

1. Click **Bookings** tab
2. Select Customer, Hotel, Room Type
3. Choose Check-in and Check-out dates
4. System auto-calculates nights and total cost
5. Click **Create Booking**

## 🔄 Core Workflows

### Workflow 1: Setting Up a New Hotel Block

**Scenario:** Secured 50 rooms at Grand Hyatt for Feb 4-6

```
1. Add Hotel → "Grand Hyatt"
2. Add Room Type → "Deluxe Room" at $250/night
3. Set Inventory → 50 rooms for Feb 4-6
4. Ready to accept bookings
```

### Workflow 2: Processing Bookings

```
1. Check availability in Room Inventory tab
2. If available → Create booking in Bookings tab
3. System auto-updates inventory
4. Review confirmation on Dashboard
```

### Workflow 3: Pre-Deadline Reconciliation

**Scenario:** Feb 1 deadline to release unused rooms for Feb 4-6

```
1. Room Inventory tab → Select hotel and room type
2. Review 30-day overview:
   - Feb 4: 35/50 booked (70%)
   - Feb 5: 42/50 booked (84%)
   - Feb 6: 28/50 booked (56%)
3. Check Reconciliation Summary
4. Decision: Release unused rooms or request more
5. Adjust inventory accordingly
```

## 📤 Import & Export

### Export Data

#### Export Everything (Excel)
```
Dashboard tab → 📊 Export All Data to Excel
```
Downloads `hotel_booking_data.xlsx` with 5 sheets:
- Hotels
- Room Types
- Customers
- Bookings
- Inventory

#### Export Individual Sections (CSV)
- Hotels tab → Export Hotels
- Customers tab → Export Customers
- Bookings tab → Export Bookings

### Import Data

#### Hotels CSV Format
```csv
Hotel Name,Location,Contact
Grand Hyatt,Hong Kong,+852 2588 1234
Mandarin Oriental,Central,+852 2522 0111
```

#### Customers CSV Format
```csv
Customer Name,Email,Phone
John Smith,john@example.com,+1234567890
Jane Doe,jane@example.com,+0987654321
```

#### Bookings CSV Format
```csv
Customer,Hotel,Room Type,Check-in,Check-out,Nights,Rate/Night,Total Cost
John Smith,Grand Hyatt,Deluxe Room,2025-02-04,2025-02-07,3,250,750
```

**⚠️ Important:** Customer names, hotel names, and room types must match existing records exactly.

## 💾 Backup & Restore

### Creating Backups

**Recommended Schedule:**
- **Weekly:** Export all data to Excel
- **Before bulk operations:** Create backup
- **Monthly:** Archive for long-term storage

**Steps:**
```
1. Dashboard tab → Export All Data to Excel
2. Save as: hotel_booking_backup_2025-02-04.xlsx
3. Store in Google Drive, Dropbox, or local backup folder
```

### Restoring Data

**From Excel Backup:**
```
1. Open backup Excel file
2. Save each sheet as separate CSV:
   - Hotels.csv
   - Customers.csv
   - Bookings.csv
3. Import in order:
   - Import Hotels
   - Manually add Room Types
   - Import Customers
   - Import Bookings
```

### Moving to Another Computer

**Method 1: Export/Import**
```
Computer A: Export all data to Excel
Computer B: Import all data from Excel
```

**Method 2: Manual Browser Copy** (Advanced)
```javascript
// On source computer (F12 Console):
localStorage.getItem('hotelBookingData')

// Copy output, then on target computer:
localStorage.setItem('hotelBookingData', 'PASTE_HERE')
```

## 🐛 Troubleshooting

### Data Disappeared

**Causes:**
- Browser cache cleared
- Using different browser
- Incognito/private mode

**Solution:**
- Restore from Excel backup
- Always export before clearing browser data
- Use same browser consistently

### Cannot Create Booking - "No rooms available"

**Causes:**
- Inventory not set for those dates
- Rooms fully booked

**Solution:**
```
1. Room Inventory tab → Check availability
2. If inventory not set → Set inventory first
3. If fully booked → Add more rooms or choose different dates
```

### Imported Data Not Showing

**Causes:**
- CSV format incorrect
- Names don't match (for bookings)
- File encoding issues

**Solution:**
- Verify CSV headers match templates
- Check names match exactly (case-sensitive)
- Ensure no extra commas or line breaks

## ✨ Best Practices

### Daily Tasks
- [ ] Review dashboard for active bookings
- [ ] Check new booking requests
- [ ] Verify inventory for upcoming dates

### Weekly Tasks
- [ ] Export full backup to Excel
- [ ] Review occupancy rates
- [ ] Identify low availability dates
- [ ] Plan inventory adjustments

### Monthly Tasks
- [ ] Generate comprehensive report
- [ ] Archive old bookings
- [ ] Analyze booking patterns
- [ ] Update room rates if needed

### Data Management Tips

1. **Regular Backups** - Weekly Excel exports minimum
2. **Consistent Naming** - Makes searching easier
3. **Set Inventory Early** - Don't wait for booking requests
4. **Monitor Occupancy** - Track trends for better planning
5. **Keep Buffer Rooms** - 10-15% for VIP/urgent requests

### Inventory Management Rules

- **Green dates (>20% available)** → Safe
- **Orange dates (≤20% available)** → Action needed
- **Red dates (0% available)** → Fully booked
- **80% occupancy rule** → Below 80% near deadline = consider releasing

## 🎨 Color Coding

| Color | Availability | Action Required |
|-------|-------------|-----------------|
| 🟢 Green | >20% available | None - good availability |
| 🟠 Orange | ≤20% available | Monitor closely |
| 🔴 Red | Fully booked | No rooms available |

## 📊 Dashboard Metrics

- **Total Bookings** - All-time booking count
- **Total Room Nights** - Sum of all nights booked
- **Total Revenue** - Sum of all booking costs
- **Active Bookings** - Currently ongoing stays
- **Occupancy Rate** - (Booked ÷ Total) × 100

## 🔒 Security & Privacy

### Data Storage
- All data stored **locally in browser**
- No external servers or databases
- No user accounts required
- Data remains on your computer only

### Access Control
- Browser-based access (anyone with computer access can view)
- Use computer password protection
- Lock screen when away
- Consider browser profiles for separation

### Data Loss Prevention
1. Regular backups (weekly minimum)
2. Multiple backup locations (cloud + local)
3. Date your backup files
4. Test restores periodically

## 💡 Tips & Tricks

### Keyboard Shortcuts
- **Tab** - Navigate between form fields
- **Enter** - Submit forms
- **Escape** - Cancel operations

### Efficient Data Entry
- Import bulk data via CSV
- Prepare data in Excel first
- Use consistent naming conventions

### Reconciliation Tips
- 80% occupancy rule for release decisions
- Keep 10-15% buffer for VIPs
- Compare with same period last year
- Track booking velocity (bookings per day)

## 📱 Browser Compatibility

| Browser | Supported | Notes |
|---------|-----------|-------|
| Chrome | ✅ | Recommended |
| Firefox | ✅ | Fully supported |
| Safari | ✅ | Fully supported |
| Edge | ✅ | Fully supported |
| Opera | ✅ | Fully supported |

**Requirements:**
- Modern browser with localStorage support
- JavaScript enabled
- No plugins or extensions required

## 🏗️ Technical Details

### Technology Stack
- **Frontend:** HTML5, CSS3, JavaScript (ES6+)
- **Storage:** Browser localStorage API
- **Export:** SheetJS (xlsx) library
- **No Backend Required**

### Data Storage
- Maximum localStorage: ~5-10MB (browser dependent)
- Typical usage: <1MB for hundreds of bookings
- Data persists across sessions
- Cleared only when browser cache cleared

### File Structure
```
hotel-booking-manager/
└── index.html          # Single-file application
```

## 📖 Glossary

| Term | Definition |
|------|------------|
| **Room Night** | One room occupied for one night |
| **Occupancy Rate** | Percentage of rooms booked vs. available |
| **Inventory** | Total rooms allocated before bookings |
| **Available** | Rooms remaining after bookings |
| **Reconciliation** | Review process to release/request rooms |
| **Buffer** | Extra rooms kept for last-minute bookings |
| **Room Block** | Group of rooms allocated for specific dates |

## 🤝 Contributing

This is a standalone project, but suggestions are welcome:

1. Fork the repository
2. Create your feature branch
3. Submit a pull request

## 📄 License

This project is licensed under the MIT License - feel free to use, modify, and distribute.

## 🔗 Links

- **Live Demo:** `https://yourusername.github.io/hotel-booking-manager`
- **Download User Guide:** [PDF Documentation](./docs/hotel-booking-guide.pdf)

## 📞 Support

For issues or questions:
- Review the [Troubleshooting](#troubleshooting) section
- Check the [Best Practices](#best-practices) guide
- Refer to the complete [User Guide PDF](./docs/hotel-booking-guide.pdf)

## 🎯 Roadmap

Future enhancements under consideration:
- [ ] Multi-language support
- [ ] Dark mode
- [ ] Advanced filtering and search
- [ ] Email confirmation templates
- [ ] Custom report builder
- [ ] Mobile app version

## ⚡ Quick Reference

### Essential Commands

| Action | Location | Shortcut |
|--------|----------|----------|
| Add Hotel | Hotels tab | Fill form → Add |
| Create Booking | Bookings tab | Select → Create |
| Check Availability | Room Inventory | View 30-day grid |
| Export Backup | Dashboard | Export All Data |
| Import Data | Each tab | Import button |

### Status Indicators

- ✅ Booking confirmed and inventory updated
- ⚠️ Low availability warning
- ❌ No rooms available
- 🔄 Loading data
- 💾 Data saved automatically

---

**Built with ❤️ for efficient hotel booking management**

**Version:** 1.0.0  
**Last Updated:** November 23, 2025  
**Maintained by:** Your Team

---

## 🌟 Star this repository if you find it helpful!
