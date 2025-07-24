# LinkedIn Profile Scraper

🔍 A comprehensive Streamlit application for extracting and analyzing LinkedIn profile information with a focus on HR professionals and certifications.

## Features

### Core Functionality
- **Bulk Profile Processing**: Process multiple LinkedIn profiles from CSV/Excel files or manual input
- **HR-Focused Analysis**: Specialized detection and analysis of HR-related profiles
- **Certification Tracking**: Extract and categorize HR certifications (SHRM, HRCI, WorldatWork, etc.)
- **Data Export**: Export results to CSV or Excel formats with summary statistics
- **Search & Filter**: Advanced filtering and search capabilities for processed data

### Key Capabilities
- ✅ Validate LinkedIn profile URLs
- ✅ Extract profile information (name, company, job title, location)
- ✅ Identify HR-related positions and departments
- ✅ Map and categorize professional certifications
- ✅ Generate comprehensive reports with analytics
- ✅ Real-time progress tracking during processing

## Installation

### Prerequisites
- Python 3.7 or higher
- pip package manager

### Required Dependencies
```bash
pip install streamlit pandas requests beautifulsoup4 openpyxl xlsxwriter
```

### Quick Install
```bash
git clone <repository-url>
cd linkedin-profile-scraper
pip install -r requirements.txt
```

## Usage

### Starting the Application
```bash
streamlit run linkedin_scraper.py
```

The application will open in your default web browser at `http://localhost:8501`

### Input Methods

#### 1. File Upload
- Upload CSV or Excel files containing LinkedIn profile URLs
- Select the column containing the URLs
- Supported formats: `.csv`, `.xlsx`, `.xls`

#### 2. Manual Entry
- Enter LinkedIn profile URLs directly in the text area
- One URL per line
- Format: `https://www.linkedin.com/in/username`

### Processing Workflow

1. **Upload/Enter URLs**: Provide LinkedIn profile URLs via file upload or manual entry
2. **Configure Filters**: 
   - Filter for HR-related profiles only
   - Filter for certified professionals only
3. **Process Profiles**: Click "Start Processing" to begin extraction
4. **View Results**: Analyze results in the Results tab
5. **Search & Filter**: Use the Search tab for detailed filtering
6. **Export Data**: Download results as CSV or Excel files

## Application Structure

### Main Tabs

#### 📤 Upload & Process
- File upload interface
- Manual URL entry
- Processing configuration and execution
- Real-time progress tracking

#### 🔍 Search Profiles
- Search by name, company, or certification
- Advanced filtering options
- Real-time search results

#### 📊 Results
- Comprehensive data overview
- Summary statistics and metrics
- Data export options
- Certification analysis charts

## Data Output Structure

### Profile Information
| Column | Description |
|--------|-------------|
| `profile_url` | Original LinkedIn profile URL |
| `profile_name` | Full name from profile |
| `company_name` | Current company |
| `job_title` | Current position title |
| `department` | Department/division |
| `location` | Geographic location |
| `is_hr_related` | Boolean flag for HR-related roles |

### Certification Details
| Column | Description |
|--------|-------------|
| `certification` | Certification name/code |
| `certification_provider` | Issuing organization |
| `certification_type` | Category of certification |
| `certification_issued` | Issue date |
| `certification_renewal` | Renewal/expiration date |

## Supported HR Certifications

### SHRM (Society for Human Resource Management)
- **SHRM-CP**: SHRM Certified Professional
- **SHRM-SCP**: SHRM Senior Certified Professional
- **SHRM-AP**: SHRM Asia Pacific

### HRCI (HR Certification Institute)
- **PHR**: Professional in Human Resources
- **SPHR**: Senior Professional in Human Resources
- **GPHR**: Global Professional in Human Resources

### HRPA (Human Resources Professionals Association)
- **CHRP**: Chartered Human Resources Professional
- **CHRL**: Chartered Human Resources Leader
- **CHRE**: Chartered Human Resources Executive

### WorldatWork
- **CCP**: Certified Compensation Professional
- **CBP**: Certified Benefits Professional
- **GRP**: Global Remuneration Professional

## Configuration Options

### Filters
- **HR-related profiles only**: Filter results to show only HR professionals
- **Certified professionals only**: Show only profiles with identified certifications

### Search Capabilities
- **Name search**: Find profiles by individual names
- **Company search**: Filter by company/organization
- **Certification filter**: Filter by specific certification types

## Technical Architecture

### Core Components

#### LinkedInScraper Class
- **Profile Validation**: Validates LinkedIn URL format
- **Data Extraction**: Simulated profile data extraction (demo mode)
- **HR Detection**: Identifies HR-related roles using keyword matching
- **Certification Mapping**: Maps certifications to providers and types

#### Key Methods
- `is_valid_linkedin_url()`: URL validation
- `extract_profile_data()`: Profile information extraction
- `is_hr_related()`: HR role detection
- `process_profiles()`: Batch processing with progress tracking

## File Structure
```
linkedin-profile-scraper/
│
├── linkedin_scraper.py      # Main application file
├── requirements.txt         # Python dependencies
├── README.md               # This file
└── docs/
    └── DESCRIPTION.md      # Detailed description
```

## Sample Input Format

### CSV File Example
```csv
linkedin_url,name,company
https://www.linkedin.com/in/john-doe,John Doe,ABC Corp
https://www.linkedin.com/in/jane-smith,Jane Smith,XYZ Inc
```

### Manual Input Example
```
https://www.linkedin.com/in/hr-professional-1
https://www.linkedin.com/in/talent-manager-2
https://www.linkedin.com/in/recruiter-3
```

## Export Formats

### CSV Export
- Single sheet with all profile and certification data
- Comma-separated values format
- Compatible with Excel and other spreadsheet applications

### Excel Export
- **Main Sheet**: Complete profile and certification data
- **Summary Sheet**: Key metrics and statistics
- Formatted for easy analysis and reporting

## Performance Considerations

- **Rate Limiting**: Built-in delays to respect server limits
- **Batch Processing**: Efficient handling of multiple profiles
- **Progress Tracking**: Real-time updates during processing
- **Error Handling**: Graceful handling of invalid URLs and failed requests

## Limitations & Considerations

### Current Implementation
- **Demo Mode**: Uses simulated data for demonstration purposes
- **Rate Limiting**: Includes delays for responsible scraping
- **URL Validation**: Basic LinkedIn URL format checking

### Production Considerations
- **LinkedIn API**: Consider using official LinkedIn API for production use
- **Terms of Service**: Ensure compliance with LinkedIn's ToS
- **Data Privacy**: Implement appropriate data handling and privacy measures
- **Authentication**: May require LinkedIn authentication for full access

## Troubleshooting

### Common Issues

#### "Invalid LinkedIn URLs"
- Ensure URLs follow format: `https://www.linkedin.com/in/username`
- Check for typos in URL format
- Verify URLs are accessible

#### "No data could be extracted"
- Check internet connection
- Verify URLs are valid and accessible
- Try processing smaller batches

#### File Upload Errors
- Ensure file is in supported format (CSV, Excel)
- Check that URL column contains valid LinkedIn URLs
- Verify file is not corrupted

## Contributing

### Development Setup
1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Run locally: `streamlit run linkedin_scraper.py`

### Code Style
- Follow PEP 8 guidelines
- Use meaningful variable names
- Include docstrings for functions
- Add comments for complex logic

## License

This project is provided as-is for educational and demonstration purposes. Users are responsible for ensuring compliance with applicable terms of service and regulations.

## Support

For issues, questions, or contributions:
1. Check the troubleshooting section
2. Review the code documentation
3. Create an issue with detailed information about the problem

---

**⚠️ Important Notice**: This application is for demonstration purposes. In production environments, ensure compliance with LinkedIn's Terms of Service, data privacy regulations (GDPR, CCPA), and implement proper authentication and rate limiting.
