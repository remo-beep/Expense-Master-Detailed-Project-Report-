Expense Master – Detailed Project Report 
Developed by: Kamogelo Makananisa and kgomotso kgaladi 
1. Project Overview
Expense Master is an Android-based personal finance tracking application designed to help users efficiently monitor their expenses, manage budgets, and improve their spending habits. It provides powerful visual tools, interactive charts, and gamified elements to make money management more engaging and insightful.
________________________________________
2. Design Considerations
The app was built with user-centered design principles, balancing functionality, aesthetics, and accessibility. Key design considerations included:
•	Responsiveness: Layouts use ScrollView, RelativeLayout, and LinearLayout with dynamic positioning to ensure compatibility across devices.
•	Usability: Large buttons, intuitive navigation, and logical grouping of functions make the app user-friendly.
•	Visual Appeal: Custom backgrounds (@drawable/ex9, @drawable/memo), icons, and color-tinted buttons provide a polished interface.
•	Accessibility: Voice input for descriptions and large, readable fonts improve accessibility.
•	Theme Support: Support for both dark and light modes, toggled from the home page with a button, to enhance visual comfort for all users.
________________________________________
3. GitHub & GitHub Actions Integration
GitHub Repository
•	Used for full version control with branches for major features.
•	Commit messages follow conventional format (e.g., feat: add bar chart for category spend, fix: validate voice input).
•	Collaborative work was facilitated via pull requests.
GitHub Actions
•	CI/CD workflows were implemented using GitHub Actions:
o	Build Verification: Android build run on every push using actions/setup-java and gradlew assemble.
o	Lint Checks: Automatic code quality checks with ktlint.
o	Unit Tests: All validation and data functions tested using JUnit.
o	APK Generation: Auto-generated APK for testing on emulator or real device.
________________________________________
4. Compulsory Features Implementation
 Bar Graph by Category Over Date Range
•	Implemented using MPAndroidChart's BarChart.
•	Users pick start and end dates to generate category-wise spending visuals.
•	Color-coded bars show whether spending exceeded or remained below min/max limits.
•	A legend explains red (Max), green (Min), and blue (Normal) ranges.
 Spending Goals Line Chart (30-Day Trend)
•	LineChart displays daily/weekly trends vs goals.
•	Overlays of minimum and maximum thresholds.
•	Easy navigation using “Back” and “Home” buttons.
•	Label: “Spending vs Goals (Last 30 Days)”.
Gamification with Badges
•	Users receive badges (displayed using ImageView) based on behavior:
o	e.g., “Budget Hero” for staying under target, “Smart Saver” for multiple category control.
•	Badge and reward description shown in the RewardsActivity.
________________________________________


5. Additional Features Implemented
Light/Dark Mode Toggle
•	A button on the home page allows toggling between light and dark themes.
•	AppCompatDelegate used to apply mode across all activities.
•	Theme preference stored in SharedPreferences.
 PDF Report Generation
•	Button labeled Generate PDF Report on the home page.
•	Exports selected data (expense list, summaries, charts) as a professionally formatted PDF using iText.
•	Saved to internal storage with a timestamped filename.
 Voice Description Input
•	Instead of typing, users can tap the mic icon to record expense descriptions.
•	Integrated with SpeechRecognizer API.
•	Option to cancel voice input via Cancel button.
•	Improves speed and usability for visually impaired or multitasking users.
________________________________________
6. UI Architecture Summary
Home Page
•	Access to all core modules: Add Expense, Manage Categories, View/Set Budget, Rewards, Reports.
•	Background image for branding (@drawable/memo).
•	Footer with app credits.
 Add Expense Page
•	Fields for amount, dates, category, description.
•	Voice input, photo attachment, and buttons to navigate to graphs or reward system.
•	Integrated validations and receipt support.
 Graph Views
•	Includes both Bar and Line Charts.
•	Clear navigation and legends to interpret data.
•	Responsive layout even in landscape orientation.
 Rewards Page
•	Displays earned badge (ImageView) and description (TextView).
•	Motivates users to improve budgeting behavior.
________________________________________
7. Technical Summary
Component	Library/API Used	Description
Bar Graph	MPAndroidChart	Spending per category
Line Chart	MPAndroidChart	Trend vs goals
Voice Input	SpeechRecognizer	Voice-to-text for descriptions
PDF Reports	iText (or PDFDocument)	Custom financial summaries
Theme Toggle	AppCompatDelegate	Dynamic dark/light switch
SQLite	Android SQLiteOpenHelper	Local data persistence
GitHub Actions	GitHub CI	Automated testing & build
________________________________________
8. Challenges & Resolutions
•	Chart Scaling: Adjusted layout_weight and BarChart margins to ensure proper rendering on small screens.
•	Voice Recognition Errors: Added cancel and retry logic for inaccurate transcriptions.
•	PDF Layout Formatting: Used tables and spacing to maintain clean formatting across screen sizes.
•	Theme Switching Flicker: Resolved using recreate() and theme persistence.
________________________________________
9. Conclusion
Expense Master successfully integrates practical financial tools with a user-friendly and modern design. The use of GitHub, CI/CD, and feature-rich additions like voice input, PDF export, and gamified rewards makes it a well-rounded, scalable application for personal expense management.

