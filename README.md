# ResumeAnalyzer

A Python-based resume analyzer that automatically extracts and evaluates resume content from PDF files. This tool categorizes key information including skills, education, experience, certifications, and soft skills, then provides a match percentage against your required qualifications.

## Features

- **PDF Text Extraction**: Automatically extracts text from PDF resume files
- **Multi-Category Analysis**: Evaluates resumes across five key categories:
  - Technical Skills
  - Education & Qualifications
  - Work Experience
  - Certifications
  - Soft Skills
- **Skill Matching**: Compares extracted skills against required skills and calculates match percentage
- **Gap Identification**: Highlights missing required skills for easy reference
- **Structured Output**: Provides organized, easy-to-read analysis results

## Requirements

- Python 3.7+
- PyPDF2 (for PDF text extraction)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/ResumeAnalyzer.git
cd ResumeAnalyzer
```

2. Install required dependencies:
```bash
pip install PyPDF2
```

## Usage

### Basic Example

```python
from ResumeAnalyzer import extract_text_from_pdf, analyze_resume, categories

# Extract text from a PDF resume
resume_text = extract_text_from_pdf("path/to/resume.pdf")

# Define required skills to match against
required_skills = ["python", "machine learning", "numpy", "pandas"]

# Analyze the resume
results, match_percentage, missing_skills = analyze_resume(
    resume_text, 
    categories, 
    required_skills
)

# View results
print(f"Skill Match: {match_percentage:.2f}%")
print(f"Missing Skills: {missing_skills}")
```

### Output

The analyzer returns:
- **Results**: Dictionary containing all found items organized by category
- **Match Percentage**: Percentage of required skills found in the resume (0-100%)
- **Missing Skills**: List of required skills not found in the resume

## How It Works

1. **Text Extraction**: Reads PDF file and extracts all text, converting to lowercase for consistent matching
2. **Categorization**: Scans extracted text against predefined keyword lists for each category
3. **Skill Matching**: If required skills are provided, calculates what percentage is present
4. **Gap Analysis**: Identifies missing skills to help guide resume improvements

## Supported Categories

| Category | Keywords |
|----------|----------|
| **Skills** | Python, Java, C, C++, Machine Learning, Deep Learning, SQL, NumPy, Pandas |
| **Education** | B.Tech, M.Sc, PhD, University, College, GPA |
| **Experience** | Internship, Worked at, Years of experience, Project |
| **Certifications** | AWS Certified, Coursera, Udemy, Oracle Certified |
| **Soft Skills** | Communication, Teamwork, Leadership, Problem Solving |

*Note: Keyword lists can be customized by modifying the `categories` dictionary*

## Example Use Cases

- **Job Application Screening**: Quickly assess how well a resume matches job requirements
- **Resume Improvement**: Identify missing skills or qualifications to target
- **Bulk Resume Analysis**: Evaluate multiple resumes against the same job criteria
- **Skill Gap Analysis**: Understand which qualifications need development

## Customization

To customize keyword matching, modify the `categories` dictionary:

```python
categories = {
    "skills": ["your", "keywords", "here"],
    "education": ["your", "keywords", "here"],
    # ... etc
}
```

## Limitations

- Keyword-based matching may miss variations in terminology
- PDF parsing may have issues with scanned or image-based resumes
- Accuracy depends on resume formatting and keyword relevance

## Future Enhancements

- Support for scanned PDF resumes (OCR integration)
- Natural language processing for improved skill detection
- Web interface for easier resume uploads
- Batch processing capabilities
- Export analysis results to CSV/JSON

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Questions or Issues?

If you encounter any issues or have suggestions, please open an issue on the GitHub repository.
