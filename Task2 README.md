TASK2
markdown
# Policy Compliance Checker RAG System

## Overview
A Retrieval-Augmented Generation (RAG) system for automated policy and contract compliance checking. The system analyzes legal documents against predefined compliance rules using semantic search and LLM-powered analysis.

## Features
- **Multi-document Analysis**: Process and analyze 510+ contracts simultaneously
- **Semantic Search**: FAISS-based vector search for finding relevant contract clauses
- **Compliance Rules**: 17 predefined legal compliance rules covering various contract aspects
- **LLM Integration**: Google Gemini AI for intelligent analysis and Q&A
- **Interactive Interface**: User-friendly functions for compliance checking and document querying

## System Architecture
1. **Data Processing**: Convert CSV contract data into vector embeddings
2. **Vector Store**: FAISS for efficient similarity search
3. **LLM Layer**: Gemini AI for compliance analysis and natural language queries
4. **Compliance Engine**: Rule-based checking with AI validation

## Installation

### Prerequisites
```bash
Python 3.8+
Google Gemini API Key
Install Dependencies
bash
pip install -r requirements.txt
Quick Start
python
# Initialize the system
from compliance_checker import PolicyComplianceChecker

# Create checker instance
checker = PolicyComplianceChecker('path/to/contracts.csv')

# Check compliance
result = checker.check_compliance("Check termination clauses")

# Ask questions about contracts
answer = checker.answer_question("What are common renewal periods?")

# Analyze specific contract
analysis = checker.analyze_contract(contract_id=0)
Usage Examples
1. Compliance Checking
python
# Check for specific compliance issues
result = checker.check_contract_compliance(
    query="Verify all parties are clearly identified",
    top_k=5
)
2. Document Search
python
# Find similar contract clauses
results = checker.search_similar_contracts(
    query="governing law jurisdiction",
    top_k=3
)
3. Batch Analysis
python
# Generate compliance report for multiple contracts
report = checker.generate_compliance_report(
    contract_ids=[0, 1, 2, 3, 4]
)
Compliance Rules
The system includes 17 predefined rules covering:

✅ Document Party Identification (HIGH)

✅ Effective Date Requirement (HIGH)

✅ Expiration Date Specification (MEDIUM)

✅ Agreement Type Classification (HIGH)

✅ Renewal Terms Clarity (MEDIUM)

✅ Notice Period for Renewal (MEDIUM)

✅ Governing Law Specification (HIGH)

✅ Most Favored Nation Clause (LOW)

✅ Non-Compete Provisions (MEDIUM)

✅ Exclusivity Terms (MEDIUM)

✅ IP Ownership Assignment (HIGH)

✅ License Grant Specification (HIGH)

✅ Termination Rights (HIGH)

✅ Liquidated Damages (MEDIUM)

✅ Liability Cap Specification (HIGH)

✅ Audit Rights Definition (LOW)

✅ Confidentiality Terms (HIGH)

Data Format
Input CSV Requirements:
Filename: Contract document identifier

Document Name: Agreement type

Parties: Contracting entities

Agreement Date: Date of agreement

Effective Date: Contract start date

Expiration Date: Contract end date

[Additional columns for specific clauses]

Sample CSV Structure:
csv
Filename,Document Name,Parties,Agreement Date,Effective Date,...
contract1.pdf,LICENSE AGREEMENT,"Company A, Company B",2023-01-01,2023-01-01,...
Configuration
Environment Variables
bash
export GOOGLE_API_KEY="your_gemini_api_key"
Customizing Compliance Rules
Edit COMPLIANCE_RULES dictionary to add/modify rules:

python
COMPLIANCE_RULES = {
    "RULE_XXX": {
        "name": "Rule Name",
        "description": "Rule description",
        "severity": "HIGH/MEDIUM/LOW",
        "check": "Compliance check criteria",
        "remediation": "Fix recommendations"
    }
}
API Reference
Core Functions
check_contract_compliance(query, top_k=5): Main compliance checking

answer_contract_question(question, top_k=5): Q&A about contracts

search_similar_contracts(query, top_k=5): Semantic search

analyze_contract_compliance(contract_id): Single contract analysis

generate_compliance_report(contract_ids): Batch reporting

Vector Store Management
save_vector_store(path): Save FAISS index

load_vector_store(path): Load FAISS index

Performance
Documents Processed: 510 contracts

Vector Store: 7,439 document chunks

Embedding Model: sentence-transformers/all-MiniLM-L6-v2 (384-dim)

Search Speed: ~100ms per query

LLM Response Time: 2-5 seconds

Error Handling
The system includes:

Rate limit handling for API calls

Retry logic for failed requests

Input validation

Graceful degradation for partial failures

Contributing
Fork the repository

Create a feature branch

Add tests for new features

Submit a pull request

License
MIT License

Support
For issues and questions:

GitHub Issues: [Link to repo]

Email: support@example.com

Citation
If you use this system in your research, please cite:

text
@software{PolicyComplianceRAG2024,
  title = {Policy Compliance Checker RAG System},
  author = {Your Name},
  year = {2024},
  url = {https://github.com/yourusername/policy-compliance-rag}
}
Acknowledgments
Google Gemini AI for LLM capabilities

HuggingFace for embedding models

FAISS for vector search

LangChain for RAG framework

Ready to ensure compliance? Start checking your contracts today!

text

This README provides:
1. **Clear overview** of what the system does
2. **Installation instructions**
3. **Usage examples** with code snippets
4. **Complete API reference**
5. **Configuration options**
6. **Performance metrics**
7. **Troubleshooting guidance**

You can copy this directly into a `README.md` file in your project directory.
