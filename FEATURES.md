# Features & Usage Guide

## 📊 Dashboard Tab

### KPI Cards

#### 1. Total Completion
- **Shows**: Overall progress percentage
- **Calculation**: (Total checkmarks across all standards) / 100
- **Visual**: Progress bar that fills as you mark items complete
- **Target**: 100% = All standards completed for at least one resource

#### 2. Standards Mastered
- **Shows**: Number of standards mastered out of 25
- **Criteria**: A standard is "Mastered" when you complete:
  - ✓ Lecture (watched the video) AND
  - ✓ Plus 2+ of: Study Hub, BPP Kit, or Kaplan Kit
- **Example**: If you check Lecture + Hub + BPP, status = Mastered
- **Use**: Track how many standards you're truly ready for

#### 3. Exam Readiness
- **Shows**: Your estimated exam preparation level
- **Levels**:
  - 🔴 **Foundational** (0-40%) - Starting out, foundational knowledge
  - 🟡 **Competent** (40-80%) - Good coverage, needs refinement
  - 🟢 **Exam Ready** (80%+) - Ready to sit the exam
- **Based on**: Your overall completion percentage
- **Note**: Section C practice results also influence readiness

---

### Progress Charts

#### Doughnut Chart: Progress by Category
Shows completion % for each of the 4 standard groups:

| Category | Color | Standards |
|----------|-------|-----------|
| Non-Current Assets (NCA) | Blue | 7 standards (IAS 16, 23, 40, etc.) |
| Specialized Standards | Indigo | 6 standards (IAS 2, 41, 37, etc.) |
| Reporting & Analysis | Green | 8 standards (IFRS 15, IAS 12, etc.) |
| Consolidation | Amber | 4 standards (MCQ, SOPL, SOFP, Framework) |

**Use**: Identify which category needs more focus

---

### Activity Feed & Tips

- **Recent Activity**: Shows last updates and study reminders
- **Section C Tip**: Highlights that Consolidation + Ratios = 40% of exam
- **Strategy**: Prioritize these high-value areas for better exam scores

---

## 📋 Syllabus Tracker Tab

### Interactive Matrix

A comprehensive table with 25 rows (one per standard) and columns for:

| Column | Purpose | Interaction |
|--------|---------|-------------|
| **Topic/Standard** | Name and category | Click to expand (future feature) |
| **Lecture** | Checkbox for lecture completion | Click to toggle |
| **Hub** | Checkbox for Study Hub completion | Click to toggle |
| **BPP Kit** | Checkbox for BPP practice completion | Click to toggle |
| **Kaplan Kit** | Checkbox for Kaplan practice completion | Click to toggle |
| **Status** | Progress indicator badge | Auto-calculated |

### Status Badges

- 🟢 **Mastered** (Green) - 100% complete (all 4 resources done)
  - Indicates deep mastery of this standard
- 🔵 **Progressing** (Blue) - 50%+ complete (2-3 resources done)
  - Good progress, keep building
- ⚪ **Started** (Gray) - <50% complete (0-1 resources done)
  - Early stage, need more coverage

---

## 📊 Detailed Analysis Tab

### Resource Utilization Gauges

Three cards showing individual completion percentages:

#### 1. Lectures Gauge
- **Metric**: % of 25 standards where you've watched the lecture
- **Target**: 100% (all lectures watched)
- **Use**: Ensures video content coverage before practice

#### 2. Study Hub Gauge
- **Metric**: % of 25 standards where you've completed Hub unit
- **Target**: 100% (all Hub units completed)
- **Use**: Reinforces conceptual understanding

#### 3. Practice Kits Gauge
- **Metric**: % of 25 standards where you've attempted BPP OR Kaplan
- **Target**: 100% (all kits attempted)
- **Use**: Ensures exam-style practice

---

### Mastery Distribution Bar Chart

Horizontal bar chart showing absolute counts:

| Bar | Represents |
|-----|------------|
| Lectures Watched | Total # of standards with lectures completed |
| Study Hub Units | Total # of standards with Hub completed |
| Practice Kits Attempted | Total # of standards with BPP or Kaplan done |
| Standards Mastered | Total # of standards meeting mastery criteria |

**Example**: If you see [25][15][20][10]
- ✓ 25 lectures watched
- ✓ 15 Hub units completed
- ✓ 20 practice kits attempted
- ✓ 10 standards fully mastered

---

## 💾 Data Persistence

### How It Works

1. **Storage Location**: Browser's localStorage (per device/browser)
2. **Save Trigger**: Every checkbox click
3. **Data Format**: JSON object with this structure:

```json
{
  "ias16": {"lecture": true, "hub": false, "bpp": true, "kaplan": false},
  "ias23": {"lecture": true, "hub": true, "bpp": false, "kaplan": false},
  ...
}
```

### Key Points

- ✅ **Private**: Data never leaves your device
- ✅ **Automatic**: Saves instantly on every click
- ✅ **Persistent**: Survives page reloads and browser restarts
- ⚠️ **Device-specific**: Different devices/browsers have separate data
- ⚠️ **Clearing cache**: Deletes your progress (be careful!)

### Backup & Restore

**To Backup**:
1. Open DevTools (F12)
2. Console tab
3. Run: `copy(localStorage.getItem('acca_fr_state'))`
4. Save text to file

**To Restore**:
1. Open DevTools
2. Console tab
3. Run: `localStorage.setItem('acca_fr_state', 'PASTE_YOUR_JSON_HERE')`

---

## 🎯 Best Practices

### Tracking Strategy

1. **Start with Lectures**
   - Watch all ACCA video lectures first
   - Check "Lecture" box after each one
   - Builds foundation for subsequent resources

2. **Then Study Hub**
   - Complete conceptual units
   - Reinforces theory
   - Check "Hub" after completion

3. **Practice with Kits**
   - BPP first (closer to exam format)
   - Then Kaplan (alternative questions)
   - Check either or both boxes

4. **Focus on Mastery**
   - Prioritize standards at "Started" status
   - Target 3 resources minimum for each standard
   - Aim for "Mastered" status on all 25

### Study Plan Example

| Week | Focus | Action |
|------|-------|--------|
| 1-2 | NCA Standards | Watch all 7 lectures, check boxes |
| 3-4 | NCA Standards | Complete Hub units, check boxes |
| 5-6 | NCA Standards | BPP practice, check boxes |
| 7-8 | Specialized Standards | Repeat the cycle |
| 9-10 | Reporting & Analysis | Repeat the cycle |
| 11-12 | Consolidation | Repeat the cycle |
| 13+ | Revision | Use analysis tab to identify weak areas |

---

## 📈 Performance Metrics

### Understanding the Numbers

**Total Completion %**
- Formula: (Σ All checkmarks) / (25 standards × 4 resources) × 100
- At 100: All 100 boxes are checked
- At 50: About 50 boxes checked
- Use: Overall readiness indicator

**Standards Mastered Count**
- Count of standards with ≥3 resources completed
- Example: 15/25 = 15 standards fully covered
- Use: How many standards you're confident on
- Target: 25/25 for exam readiness

**Category Percentages**
- Formula per category: (Σ Category checks) / (# standards × 4) × 100
- Identifies category strengths/weaknesses
- Use: Decide where to focus revision

---

## 🔍 Tips for Exam Success

### High-Value Areas (40% of exam)
1. **Consolidation**
   - SOPL (Statement of Profit/Loss)
   - SOFP (Statement of Financial Position)
   - Group accounting concepts
   
2. **Ratio Analysis**
   - Financial interpretation
   - Performance metrics
   - Comparison analysis

**Action**: Achieve "Mastered" status on all Consolidation + Ratio standards FIRST

### Must-Know Standards
| Standard | Priority | Why |
|----------|----------|-----|
| IAS 16 | ⭐⭐⭐ | Most frequently tested |
| IFRS 15 | ⭐⭐⭐ | Revenue recognition (Section A) |
| Consolidation | ⭐⭐⭐ | 40% of marks |
| IAS 2 | ⭐⭐ | Inventory valuation |
| IFRS 9 | ⭐⭐ | Financial instruments |

---

## 🚀 Advanced Tips

### Optimize Your Study
- **Batch similar topics**: Group related IAS standards
- **Use the charts**: Identify outliers (missing resources)
- **Consistency**: Daily check-ins better than cramming
- **Review regularly**: Use analysis tab weekly

### Maximize Practice
- **All 4 resources**: Lecture + Hub + BPP + Kaplan = highest mastery
- **Exam conditions**: Take timed practice kits under test conditions
- **Error analysis**: Review mistakes in kits, then re-read relevant lecture

---

## ❓ FAQ

**Q: Do I need to check all 4 resources?**
A: No, but completing 3+ indicates true mastery. 1-2 is adequate for basics.

**Q: What's the ideal completion timeline?**
A: ~12 weeks at 2 standards/week = full coverage. Adjust based on your exam date.

**Q: Can I share my progress across devices?**
A: No, localStorage is device-specific. Backup and restore manually (see section above).

**Q: Does this replace the ACCA syllabus?**
A: No, it's a tracking tool. Study the actual standards using your resources.

**Q: Is 80% completion enough to sit the exam?**
A: Depends on your confidence. Aim for 90%+ and "Exam Ready" status for safety.

---

## 📞 Support

For issues or feature requests, please open a GitHub issue on the repository.

**Happy studying! 🎓**
