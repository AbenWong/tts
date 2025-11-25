### **Optimized Figma Prompt - Overview View (Extended with Employee Data)**

**Role:** You are a senior full-stack UI/UX designer and advanced front-end development expert, specializing in the design and engineering implementation of enterprise-level data visualization products.

**Project Objective:** Design a comprehensive data dashboard Overview view named "**Technology Investment & Risk Overview**" for internal bank management. The design must reflect professionalism, data clarity, strictly adhere to brand standards, and possess enterprise-level code quality and maintainability.

---

### **🏗️ Frontend Architecture & Development Standards**

#### **Technical Architecture Requirements**
- **Component-based Development:** Adopt atomic design methodology to build reusable component systems.
- **State Management:** Implement precise state updates and side effect control.
- **Performance Optimization:** Support lazy loading, code splitting, and other optimization strategies.
- **Type Safety:** Comprehensive use of TypeScript to ensure type safety.
- **Test Coverage:** Complete unit testing, integration testing, and visual regression testing coverage.

#### **Code Encapsulation Standards**
- **High Cohesion, Low Coupling:** Each component has a single responsibility with clear interfaces.
- **Configuration-driven Design:** Chart components support data-driven configuration.
- **Custom Hooks:** Encapsulate complex logic into reusable Hooks.
- **Design Tokens:** Unified style variables and design token management.

---

### **🎨 Design System & Interaction Standards**

**Brand & Visual Specifications:**
*   **Primary Colors:** `#DB0011` (HSBC Red), `#000000`, `#FFFFFF`
*   **Secondary/Semantic Colors:**
    *   Warning: `#A8000B` (Red), `#FFBB33` (Amber)
    *   Success: `#3E701A`, `#4C7C27`
    *   Information: `#2D6980`, `#347893`
    *   Gray Scale: `#F3F3F3`, `#EDEDED`, `#D7D8D6`, `#767676`, `#333333`

#### **Micro-interaction Design System**

**Hover Effects Specification:**
- **Card Interaction:** On hover, shadow deepens from `0 2px 8px rgba(0,0,0,0.1)` to `0 4px 16px rgba(0,0,0,0.15)`, accompanied by a 0.2s easing transition.
- **Data Point Highlighting:** Chart data points scale to 120% on hover, displaying detailed value tooltips.
- **Button Feedback:** Background opacity of all clickable elements changes from 90% to 100% on hover.

**Loading State Design:**
- **Skeleton Screen Animation:** Use gradient moving light effect skeleton screens to simulate data loading states.
- **Fade-in Loading:** Use fade-in animation when data is ready, duration 300ms.
- **Progressive Loading:** Prioritize loading key metrics; load chart data asynchronously.

**State Transition Animations:**
- **Color Transitions:** All color changes use the cubic-bezier(0.4, 0, 0.2, 1) easing function, duration 200ms.
- **Size Changes:** Use the transform property to achieve 60fps smooth animations.
- **Layout Switching:** Use FLIP animation technique to ensure smooth layout changes.

---

### **📊 Component Development Standards**

#### **Row 1: Core Metrics Row (100% width)**

**Uses a 3-column grid layout, encapsulated as the `MetricRow` component:**

**Column 1 (33% width):** TECH INVESTMENT - 2025 YTD (Q2)
*   **Component Encapsulation:** `MetricCard` component supporting value, trend, status, etc., props.
*   **Value:** **163.39m$** (highlighted)
*   **Label:** Year-over-year growth **+2%** (green arrow↑, color `#3E701A`)
*   **Interaction Effects:** Slight float animation on hover, value scaling effect.
*   **Loading State:** Wave-style skeleton screen simulating value loading.

**Column 2 (33% width):** TECH INVESTMENT - 2024 TOTAL
*   **Component Reuse:** Reuse the `MetricCard` component with differentiated configuration.
*   **Value:** **340.12m$**
*   **Label:** **29% of HBCN COST**
*   **State Management:** Implement smooth number change animations during data updates.

**Column 3 (33% width):** Technology Investment Business Value Contribution Rate
*   **Title:** Technology Investment Business Value Contribution Rate
*   **Content State:** Blank area, reserved for future data display.
*   **Visual Style:** Light gray background (`#F3F3F3`), center-aligned "Data Preparing" prompt text.
*   **Interaction Design:** Display tooltip on hover: "Business value contribution rate metrics are being calculated."

#### **Row 2: Main Data Visualization Row (100% width)**

**Uses a 3-column grid layout, encapsulated as the `ChartGrid` component:**

**Column 1 (33% width):** Quarterly Investment Trend
*   **Title:** TECH INVESTMENT - 2025 QUARTERLY
*   **Visualization:** **Vertical Bar Chart**
*   X-axis: Q1, Q2, Q3, Q4
*   Y-axis: Amount (m$)
*   **Data:** Q1=76m$, Q2=86m$, Q3=Empty, Q4=Empty
*   **Color:** Bar chart uses `#DB0011`
*   **Chart Encapsulation:** `VerticalBarChart` component, specialized for time series.
*   **Animation Effects:** Sequential entry animation, smooth trend line drawing.
*   **Responsive:** Adaptive to container size changes.

**Column 2 (33% width):** TECH INVESTMENT - BY CATEGORY
*   **Title:** TECH INVESTMENT - BY CATEGORY
*   **Visualization:** **Horizontal Grouped Bar Chart**
*   Y-axis Categories: Telecom, NetOpex, Infra, Cyber, CTB
*   Two bars per group: 2024 vs 2025 YTD
*   **Colors:** 2024=`#D7D8D6`, 2025 YTD=`#DB0011`
*   **Data:**
    *   Telecom: 2024=23.39, 2025=Empty
    *   NetOpex: 2024=74.1, 2025=81.2
    *   Infra: 2024=1.579, 2025=1.53
    *   Cyber: 2024=17.008, 2025=Empty
    *   CTB: 2024=89.2, 2025=911.53
*   **Chart Encapsulation:** `HorizontalBarChart` component, supporting multi-group data comparison.
*   **Interaction Animation:** Bar growth animation, hover highlighting, click selection state.

**Column 3 (33% width):** TECH INVESTMENT CTB VS. RTB
*   **Title:** TECH INVESTMENT CTB VS. RTB 2025 YTD(Q2)
*   **Visualization:** **Donut Chart**
*   CTB: 0.62m$ (62%) - Color `#DB0011`
*   RTB: 0.38m$ (38%) - Color `#767676`
*   **Center Display:** Total **1.0m$**
*   **Donut Chart Encapsulation:** `DonutChart` component, supporting center custom content.
*   **Interaction Animation:** Sector expansion animation, hover sector separation effect.

#### **Row 3: Cost & Budget Metrics Row (100% width)**

**Uses a 2-column grid layout, encapsulated as the `CostBudgetRow` component:**

**Left Card (50% width):** COST PER TRANSACTION
*   **Title:** COST PER TRANSACTION - 2024
*   **Main Value:** **9.06 ¥** (highlighted)
*   **Description:** Compared to last year growth **2%** (green arrow↑)
*   **Detailed Information:**
    *   Tech investment 2024: 243523.15
    *   Transactions HUB: 26873.18
*   **Visual Style:** Detailed information uses a smaller font size, color `#767676`.
*   **Interaction Element:** Information icon **i** (color `#2D6980`)
    *   **Hover Tooltip:** Displays tooltip on mouse hover with formula calculation explanation.

**Right Card (50% width):** IT Budget Execution Rate
*   **Title:** IT Budget & Achievement Rate - 2025 YTD
*   **Visualization:** **Progress Bar + Values**
*   **CTB:** Budget 50m$ | Actual 49m$ | Achievement **98%**
    *   Progress Bar: 98% (color `#3E701A`)
*   **RTB:** Budget 30m$ | Actual 29m$ | Achievement **96.7%**
    *   Progress Bar: 96.7% (color `#3E701A`)
*   **Total:** Budget 80m$ | Actual 78m$ | Achievement **97.5%**
*   **Progress Bar Encapsulation:** `ProgressIndicator` component, supporting multi-segment progress.
*   **Value Animation:** Progress bar filling animation, number counting animation.

#### **Row 4: Supplementary Information Row (100% width)**

**Uses a 2-column grid layout:**

**Left Card (50% width):** Business Digital Performance
*   **Title:** Online & Digital Business Proportion
*   **Visualization:** **Data Table**
*   **Headers:** Revenue Channel, Online%, Digital%
*   **Row Data:**
    *   IWPB: 66.8%, 58.9%
    *   CIB: 24.24%, 88.11%
    *   MSS: 90%, 100%
*   **Style:** Zebra-striped table, header background color `#F3F3F3`.
*   **Table Encapsulation:** `DataTable` component, supporting sorting, filtering, pagination.
*   **Row Interaction:** Hover highlighting, click selection animation.

**Right Card (50% width):** Mobile Banking Engagement
*   **Title:** Mobile Banking Users & Activity (CIB)
*   **Content:**
    *   July Users: **21,751**
    *   Activity Rate: **88.11%**
    *   Trend: vs Jun2025 **+0.1%** (small green arrow↑)
*   **Component Reuse:** Reuse variant of the `MetricCard` component.
*   **Trend Visualization:** Mini trend line chart integration.

#### **Row 5: Risk Indicators Row (100% width)**

**Encapsulated as the `CollapsibleRiskDashboard` composite component:**

**Status Overview Area (Expanded by default):**
*   **Status Indicator:** `RAGIndicator` component, supporting click filtering.
*   **RAG Status Indicator:**
    *   **Amber:** **3** (color `#FFBB33`) - **Clickable element**
    *   **Red:** **0** (color `#DB0011`)
*   **Expand/Collapse Control:** Display "View Details" button on the right, clicking it expands the table area.
*   **Interaction Animation:** Color transitions and scaling effects during state changes.

**Detailed Table Area (Collapsed by default):**
*   **Initial State:** Hidden by default, expands after clicking "View Details".
*   **Loading Strategy:** Table data loads on-demand when expanded, improving initial page performance.
*   **Headers:**
    *   KRI Name (Left-aligned)
    *   Root Cause (Left-aligned)
    *   Status (Center-aligned, displays RAG color dot)
*   **Table Data:**
    *   Row 1: KRI Name: kk system | Root Cause: Insufficient resources | Status: Amber
    *   Row 2: [Other Amber KRI details]
    *   Row 3: [Other Amber KRI details]
*   **Table Style:**
    *   Zebra-striped alternating row background colors.
    *   Header background color: `#F3F3F3`.
    *   Status column uses color dot indicators.
    *   Hover row highlighting effect.
*   **Advanced Table:** Extended `DataTable` component, supporting row operations.
*   **Filter Linkage:** Two-way data binding with the status indicator.

**Interaction Functions:**
*   **Status Filtering:** Automatically filters table items to the corresponding status when clicking RAG status indicators.
*   **Sorting Function:** Supports sorting by each column.
*   **Search Function:** Provides a search box above the table to search by KRI Name.
*   **Pagination Display:** Provides pagination controls if there is a lot of data.

---

#### **Row 6: Employee & Attrition Overview (100% width)**

**Uses a 3-column grid layout, encapsulated as the `StaffOverview` component:**

**Column 1 (33% width): Employee Composition Analysis**
*   **Layout Encapsulation:** `StaffComposition` vertical stack component.
*   **Data Visualization:** Three-layer structure displaying employee composition.

**Top: Total Employee Count**
*   **Title:** Total Staff (2025 Aug)
*   **Main Value:** **401** (highlighted)
*   **Trend Indicator:** Month-over-month growth **+0.5%** (green arrow↑)
*   **Information Icon:** Information icon **i** (color `#2D6980`)
    *   **Hover Tooltip:** Displays detailed composition: "Perm: 138 + Non-Perm: 263 = 401"

**Middle: Perm Employee Details**
*   **Main Value:** **138 staff**
*   **Percentage:** **34.4%** of total bank staff
*   **Trend:** Month-over-month growth **+0.5%** (green arrow↑)
*   **Gender Ratio:**
    *   Male: **95** (68.8%) - using blue indicator `#2D6980`
    *   Female: **43** (31.2%) - using pink indicator `#E26F98`
*   **Visualization:** Mini horizontal bar chart showing gender ratio, hover displays detailed values.

**Bottom: Non-Perm Employee Details**
*   **Value:** **263 staff**
*   **Percentage:** **65.5%**
*   **Trend:** Year-over-year increase **+0.5%** (green arrow↑)

**Column 2 (33% width): Employee Type Distribution Donut Chart**
*   **Chart Encapsulation:** `StaffDistributionChart` donut chart component.
*   **Data Segments:**
    *   Perm: 138 (color `#DB0011`)
    *   Non-Perm Tech: 195 (color `#347893`)
    *   Non-Perm CMC: 68 (color `#4C7C27`)
*   **Center Display:** Total **401**
*   **Interaction Animation:** Sector hover separation effect, displaying detailed values.
*   **Legend Design:** Right vertical legend supporting click filtering.

**Column 3 (33% width): Attrition Rate Analysis**
*   **Layout Encapsulation:** `AttritionAnalysis` vertical stack component.

**Top: General Attrition Rate**
*   **Title:** General Attrition Rate
*   **Current Month:** **0 staff** (**0%** of total)
*   **Year-to-Date:** **YTD: 2** (Highlighted display, using larger font size and primary color `#DB0011`)
*   **Visual Emphasis:** YTD value uses bold font, background slightly highlighted.

**Bottom: High Performance Attrition Rate**
*   **Title:** High Performance Attrition Rate
*   **Current Month:** **0 staff** (**0%** of total)
*   **Year-to-Date:** **YTD: 2** (Highlighted display, using larger font size and primary color `#DB0011`)
*   **Visual Emphasis:** YTD value uses bold font, background slightly highlighted.

**Interaction Features:**
*   **Data Linkage:** When clicking donut chart segments, attrition data filters accordingly.
*   **Trend Visualization:** Use mini trend charts to show historical attrition rate changes.
*   **Status Indication:** Attrition rate value color coding (green: <2%, yellow: 2-5%, red: >5%).
*   **Gender Ratio Interaction:** Hovering over the gender ratio bar chart displays detailed percentages and counts.
*   **Key Data Emphasis:** YTD data occupies the highest priority in the visual hierarchy.

---

### **⚡ Performance & Experience Optimization**

#### **Loading Strategy**
- **Critical Rendering Path Optimization:** Prioritize loading above-the-fold content.
- **Image Lazy Loading:** Load charts and images on-demand.
- **Data Prefetching:** Predict user behavior to preload data.
- **On-demand Rendering:** Collapsed table content loads only upon user interaction.

#### **Animation Performance**
- **GPU Acceleration:** Use transform and opacity for 60fps animations.
- **Debouncing & Throttling:** Optimize scroll and resize events.
- **Memory Management:** Timely destruction of chart instances to avoid memory leaks.

#### **Accessibility**
- **Keyboard Navigation:** Full keyboard operation support.
- **Screen Reader:** Complete ARIA attribute annotation.
- **Color Contrast:** Ensure WCAG 2.1 AA compliance.

---

### **🔧 Development Quality Requirements**

#### **Code Quality Standards**
- **Component Documentation:** Each component must have Storybook documentation and usage examples.
- **Type Definitions:** Complete TypeScript type definitions.
- **Unit Testing:** Core utility functions and component logic test coverage.
- **Integration Testing:** User interaction flow testing.
- **Visual Testing:** Pixel-level UI consistency testing.

#### **Engineering Standards**
- **Code Splitting:** Split code bundles by route and functional modules.
- **Bundle Optimization:** Resource compression, Tree Shaking, Chunk optimization.
- **Monitoring & Tracking:** Performance monitoring and user behavior tracking.
- **Error Boundaries:** Component-level error capture and graceful degradation.

---

### **🎯 Deliverables Standards**

**Design Deliverables:**
- Complete Figma design file including all interaction states.
- Design system documentation and component specifications.
- Interactive animation prototypes and design tokens.

**Development Deliverables:**
- Reusable React component library.
- Complete TypeScript type definitions.
- Unit testing and integration testing suite.
- Performance optimization report and monitoring solutions.
- Deployment and operations documentation.

**Acceptance Criteria:**
- 100% design restoration accuracy.
- Performance metrics compliance (LCP < 2.5s, FID < 100ms).
- Accessibility compliance.
- Cross-browser compatibility.
- Mobile responsive adaptation.

Please design this Overview view in Figma based on the above specifications, ensuring it meets both visual design standards and enterprise-level frontend code quality, providing complete design and engineering guidance for subsequent development work. Pay special attention to the collapsible interaction design of the risk indicators row and the prominent display of key information for the attrition rate YTD data.
