# Excursion Studio Personal Homepage (ESPH) Template ver.2

[中文版](README_zh.md) | English Version

Based on the [first version of the ESPH template](https://github.com/Excursion-Studio/Personal-Homepage-Template/), we have reconstructed it using the **React** framework to create this ESPH V2 template. For a comparison of code development and performance between the two versions, click [here (Chinese version)](summary.md).

The ESPH V2 template is a **React**-based fully functional personal academic homepage template that supports bilingual switching (Chinese and English) and light/dark theme switching. It is suitable for academics, researchers, or anyone who needs to showcase their personal experiences and achievements.

You can preview the example page [here](https://excursion-studio.github.io/Personal-Homepage-Template-v2/).

## Features

- 🌐 **Multi-language Support**: Supports Chinese and English switching, all content has corresponding Chinese and English versions
- 🎨 **Theme Switching**: Supports light and dark theme switching, theme settings are saved in local storage
- 📱 **Responsive Design**: Adapts to desktop and mobile devices, providing a good user experience
- 🔧 **Modular Design**: Each functional module has independent files, easy to maintain and extend
- 📊 **Data-driven**: All content is loaded from JSON configuration files, no need to modify code to update content
- ⚛️ **React Technology Stack**: Uses modern React technology stack, making code more concise and maintainable

## Project Structure

```
Personal-Homepage-Template-v2/
├── README.md                 # English documentation
├── README_zh.md              # Chinese documentation
├── summary.md                # React vs Vanilla JS comparison
├── index.html                # Main page file
├── assets/                   # Static resource files (React build artifacts)
├── configs/                  # Configuration files
│   ├── config.json           # Main configuration file
│   ├── en/                   # English configuration
│   └── zh/                   # Chinese configuration
└── images/                   # Image resources
    ├── experience/           # Experience-related images
    ├── homepage/             # Homepage-related images
    │   ├── info icon/        # Information icons
    │   └── photo/            # Personal photo
    └── publication/          # Publication-related images
```

## Installation and Deployment

### Local Development

1. Download or clone the project to your local machine
2. Use a local server to run the project files (due to the use of Fetch API, you may encounter cross-domain issues when directly opening HTML files)
3. Visit `http://localhost:8000` in your browser

### Deployment to GitHub Pages

1. Create a new GitHub repository
2. Upload all files to the root of the repository
3. Enable GitHub Pages in the repository settings
4. Visit the assigned GitHub Pages URL

### Deployment to Other Web Servers

1. Upload all files to your web server
2. Visit the corresponding URL

Common web providers include GitHub Pages, Google Sites, etc.

## Configuration Instructions

### Main Configuration File (configs/config.json)

This file is used to configure available languages, default language, and single language mode.

```json
{
    "availableLanguages": ["en", "zh"],
    "defaultLanguage": "en",
    "singleLanguageMode": false
}
```

- `availableLanguages`: List of available languages
- `defaultLanguage`: Default language
- `singleLanguageMode`: Whether to enable single language mode (if set to true, the language switch button will be hidden)

If set to false, the language switch button will be displayed, and both English and Chinese configuration files are required. Otherwise, only the configuration files for the corresponding language are needed.

### Personal Information Configuration

#### English Configuration (Take configs/en/info_en.json as an example)

```json
{
    "name": "Your Name",
    "address": "Your Address",
    "institution": "Your Institution",
    "googlescholar": "Google Scholar Profile",
    "github": "GitHub Profile",
    // If you don't have (or don't want to display) Google Scholar and/or GitHub accounts, you can delete the corresponding fields
    "email": "Email Address",
    "UTC": "+8"
}
```

#### Chinese Configuration (Take configs/zh/info_zh.json as an example)

```json
{
    "name": "您的姓名",
    "address": "您的地址",
    "institution": "您的机构",
    "googlescholar": "Google Scholar 个人主页",
    "github": "GitHub 个人主页",
    // 如果没有（或者不愿意展示） google scholar 和/或 github 账号，对应的字段可以删除
    "email": "邮件地址",
    "UTC": "+8"
}
```

### Other Configuration Files

Each section has corresponding configuration files, including:

- `education_en.json` / `education_zh.json`: Education experience
- `employment_en.json` / `employment_zh.json`: Work experience
- `honors_en.json` / `honors_zh.json`: Honors and awards
- `news_en.json` / `news_zh.json`: News and updates
- `papers_en.json` / `papers_zh.json`: Academic papers
- `patents_en.json` / `patents_zh.json`: Patents
- `reviewer_en.json` / `reviewer_zh.json`: Reviewer experience
- `teaching_en.json` / `teaching_zh.json`: Teaching experience
- `intro_en.txt` / `intro_zh.txt`: Personal introduction

## Customizing Content

### Modifying Personal Information

Personal information will be displayed in the left information bar of the Home section. Edit `configs/en/info_en.json` and/or `configs/zh/info_zh.json` files to update your personal information. The specific fields are as shown in the above example.

### Adding Education Experience

Education experience will be displayed in the first tab of the Experiences section. Add your education experience in `configs/en/education_en.json` and/or `configs/zh/education_zh.json`.

```json
[
    {
        "logoSrc": "university_logo.png", // University logo image path, placed in images/experiences
        "school": "University Name",
        "details": [
            {
                "degree": "Degree",
                "department": "Department",
                "time": "Start year - End year (or current)",
                "tutor": "Supervisor Name",
                "dissertation": "Thesis Title",
                // If you don't have (or don't want to display) a supervisor and/or thesis, you can delete the corresponding fields
            },
            // If you have multiple different experiences at the same institution, you can continue adding them here...
        ]
    },
    // If you have different experiences at other universities, you can continue adding them here...
]
```

### Adding Work Experience

Work experience will be displayed in the second tab of the Experiences section. Add your work experience in `configs/en/employment_en.json` and/or `configs/zh/employment_zh.json`. If you don't have work experience, you can delete or empty the corresponding json file, and the corresponding section will not be displayed.

```json
[
    {
        "logoSrc": "company_logo.png", // Company logo image path, placed in images/experiences
        "company": "Company Name",
        "details": [
            {
                "position": "Position",
                "department": "Department",
                "time": "Start year - End year",
                "project": "Project Name",
                // If you don't have (or don't want to display) a project, you can delete the corresponding field
            },
            // If you have multiple different experiences at the same company, you can continue adding them here...
        ]
    },
    // If you have different experiences at other companies, you can continue adding them here...
]
```

### Adding Academic Papers

Academic papers will be displayed in the first tab of the Publications section. Add your academic papers in `configs/en/papers_en.json` and/or `configs/zh/papers_zh.json`.

```json
{
    "Year": [
        {
            "title": "Paper Title",
            "authors": "<u>Author 1</u>, Author 2, Author 3",
            // You can use <u> tag to underline yourself
            "type": "Paper type, such as Conference / Journal / Workshop / In submission",
            "journal": "Journal Name",  // If it's a conference or workshop, replace this line with "conference": "Conference Name"
            "abbr": "Journal/Conference abbreviation",
            "volume": "Volume", // If it's a conference or workshop, replace this line with "location": "Conference location", In submission can leave this line blank
            "image": "paper_image.png", // Paper image path, supports .png, .jpg, .gif formats, placed in images/publications
            "paperLink": "Paper link",
            "codeLink": "Code link",
            "videoLink": "Video link",
            "siteLink": "Project website link",
            // If you don't have code/video/project website, you can delete the corresponding fields
        },
        // If you have multiple different papers in the same year, you can continue adding them here...
    ],
    // If you have different papers in other years, you can continue adding them here...
}
```

### Adding Patents

Patents will be displayed in the second tab of the Publications section. Add your patents in `configs/en/patents_en.json` and/or `configs/zh/patents_zh.json`. If you don't have patent information, you can delete or empty the corresponding json file, and the corresponding section will not be displayed.

```json
[
    {
        "type": "Patent Type",
        "title": "Patent Title",
        "authors": "<u>Inventor 1</u>, Inventor 2, Inventor 3",
        // You can use <u> tag to underline yourself
        "number": "Patent Number",
        "date": "Date",
        "link": "https://patent.link"
    },
    // If you have different patents, you can continue adding them here...
]
```

### Adding Honors and Awards

Honors and awards will be displayed in the third tab of the Experiences section. Add your honors and awards in `configs/en/honors_en.json` and/or `configs/zh/honors_zh.json`. If you don't have honors and awards, you can delete or empty the corresponding json file, and the corresponding section will not be displayed.

```json
[
    {
        "time": "Year",
        "award": "Award Name",
        "unit": "Awarding Unit"
    },
    // If you have different honors and awards, you can continue adding them here...
]
```

### Adding News and Updates

News and updates will be displayed in the second column on the right side of the Home section. Add your news and updates in `configs/en/news_en.json` and/or `configs/zh/news_zh.json`.

```json
[
    {
        "time": "YYYY-MM-DD",
        "content": "News content with <span style='font-style: italic'>italic text</span> if needed"
    },
    // If you have different news and updates, you can continue adding them here...
]
```
You can use HTML tags to format the content of news and updates. Here are some commonly used tags:

- `<em>italic text</em>`: Italic text
- `<u>underline text</u>`: Underline text
- `<strong>bold text</strong>`: Bold text
- `<br>`: Line break
- `<a href="website/address" target="_blank">super link</a>`: Insert hyperlink

### Adding Teaching Experience

Teaching experience will be displayed in the fourth tab of the Experiences section. Add your teaching experience in `configs/en/teaching_en.json` and/or `configs/zh/teaching_zh.json`. If you don't have teaching experience, you can delete or empty the corresponding json file, and the corresponding section will not be displayed.

```json
[
    {
        "school": "School Name",
        "course": "Course Name",
        "code": "Course Code",
        "identity": "Teaching Role",
        "season": "Season",
        "year": "Year"
    },
    // If you have different teaching experiences, you can continue adding them here...
]
```

### Adding Reviewer Experience

Reviewer experience will be displayed in the fifth tab of the Experiences section. Add your reviewer experience in `configs/en/reviewer_en.json` and/or `configs/zh/reviewer_zh.json`. If you don't have reviewer experience, you can delete or empty the corresponding json file, and the corresponding section will not be displayed.

```json
[
    {
        "conference": "Conference Name",
        "year": "Year"
    },
    {
        "journal": "Journal Name",
        "year": "Year"
    },
    // If you have different reviewer experiences, you can continue adding them here...
]
```

### Adding Personal Introduction

Personal introduction will be displayed in the first column on the right side of the Home section. Edit `configs/en/intro_en.txt` and/or `configs/zh/intro_zh.txt` files to add your personal introduction. You can use HTML tags to format the text, and common tags are mentioned in the "News and Updates" section above.

### Adding Image Resources

1. Add school/company logos to `images/experience/` directory
2. Add paper-related images to `images/publication/` directory
3. Add personal photos to `images/homepage/photo/` directory
4. Add information icons to `images/homepage/info icon/` directory

## Feature Instructions

### Language Switching

- Click the language switch button (中/EN) in the navigation bar to switch languages
- Language settings are saved in local storage, and your choice will be remembered for the next visit
- The cache is cleared when switching languages to ensure correct content loading

### Theme Switching

- Click the theme switch button (sun/moon icon) in the navigation bar to switch themes
- Theme settings are saved in local storage, and your choice will be remembered for the next visit
- All page elements have corresponding theme styles

### Responsive Design

- The template adapts to desktop and mobile devices
- On mobile devices, the navigation bar will be adjusted to a vertical layout
- All content will automatically adjust its layout according to the screen size

## Contact Information

If you have any questions or suggestions, please contact us through:

- GitHub: [https://github.com/Excursion-Studio](https://github.com/Excursion-Studio)
- Email: [excursion-studio@outlook.com](mailto:excursion-studio@outlook.com) (Studio email)