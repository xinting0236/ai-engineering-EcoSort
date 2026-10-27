## Project Name

**UniGuide AI — AI-Powered University FAQ Assistant**

## Domain

Higher Education / Student Services / Natural Language Processing / Retrieval-Augmented Generation (RAG)

## Problem Statement

University students often need to find information about academic calendars, course registration, academic regulations, and student services. This information is published across different university webpages and documents, which can make it time-consuming to locate the correct information.

UniGuide AI will use semantic retrieval and a large language model to answer students' questions using official UTM documents. It will provide source citations so students can verify the information and will indicate when the available documents do not contain a sufficient answer.

## Evidence of the Problem

**Evidence 1:** UTM publishes course registration requirements and procedures through its Academic Management Division website. Students must understand the applicable registration rules and deadlines, making accurate access to this information important.

**Source / citation:** [UTM Academic Management Division — Course Registration Guidelines](https://amd.utm.my/course-registration/)

**Evidence 2:** UTM's Faculty of Computing Student Development Hub provides separate resources for academic calendars, academic regulations, course registration timetables, and undergraduate handbooks. This demonstrates that relevant student information is available through multiple resources rather than one single FAQ page.

**Source / citation:** [UTM Faculty of Computing — Student Development Hub](https://comp.utm.my/student/home/)

## Initial Related Work (at least 3)

### Study / Solution 1: Academic FAQ Chatbot Using Retrieval-Augmented Generation

**Description:** This study develops an academic FAQ chatbot using document preprocessing, embedding-based retrieval, a vector database, and a large language model to answer questions about academic information.

**Source / citation:** [Academic FAQ Chatbot Using Retrieval Augmented Generation (2026)](https://ejournal1.unud.ac.id/index.php/jitter/article/view/4289)

**Key limitation:** A chatbot developed for a particular academic information collection may not directly support UTM's own documents, policies, and student information requirements. Its answers must also be evaluated against the relevant official sources.

### Study / Solution 2: Retrieval-Augmented Generation for Educational Applications — A Systematic Survey

**Description:** This survey reviews RAG applications in education and discusses technical components such as indexing, retrieval, and answer generation.

**Source / citation:** [Computers and Education: Artificial Intelligence (2025)](https://www.sciencedirect.com/science/article/pii/S2666920X25000578)

**Key limitation:** The survey identifies challenges such as hallucinations, outdated knowledge, and limited multimodal capabilities. A general RAG framework does not automatically guarantee correct answers or reliable citations for university information.

### Study / Solution 3: Label-Free Evaluation of Retrieval-Augmented Generation in a University Policy Chatbot

**Description:** This study evaluates a RAG chatbot for university policy documents, examining answer relevance, groundedness, and retrieval effectiveness.

**Source / citation:** [ACM Technical Symposium on Computer Science Education (2026)](https://doi.org/10.1145/3770761.3777161)

**Key limitation:** The study reports that answer relevance and groundedness remain imperfect, demonstrating that a university chatbot needs systematic evaluation rather than assuming that retrieved documents always produce correct answers.

## Engineering Gap / Limitation

Existing university information sources provide authoritative content, while RAG-based chatbots offer a more conversational way to access it. However, students may still receive incomplete, outdated, or unsupported answers if retrieval and answer generation are unreliable.

UniGuide AI addresses this practical gap by integrating semantic document retrieval, source-grounded answer generation, citations, and an insufficient-evidence fallback into one web application using official UTM information. Its performance will be measured using a prepared set of questions with expected answers and supporting document passages.

## Initial Project Objectives (2–3)

**O1:** To collect and prepare official UTM documents and webpages covering academic calendars, course registration, academic regulations, and student services for the knowledge base.

**O2:** To develop a web-based university FAQ assistant using semantic retrieval and a large language model to generate document-grounded answers with source citations and appropriate fallback behaviour.

**O3:** To evaluate the system using answer correctness, retrieval relevance, citation accuracy, unsupported-answer handling, and response latency.

## Target Users

UTM undergraduate students, particularly new students and students who need information about academic calendars, course registration, academic regulations, and university student services.

The initial version will focus on publicly accessible information and will not provide personalised academic decisions or access to private student records.

## Data Sources (at least 2)

**Source 1: UTM Academic Management Division — Course Registration Guidelines**

URL: https://amd.utm.my/course-registration/

**Purpose:** To provide information about course registration procedures, registration requirements, and relevant student guidance.

**Source 2: UTM Faculty of Computing — Student Development Hub**

URL: https://comp.utm.my/student/home/

**Purpose:** To identify official student resources, including academic calendars, academic regulations, course registration information, and undergraduate handbooks.

**Source 3: UTM Faculty of Computing — Undergraduate Resources**

URL: https://comp.utm.my/undergraduate/

**Purpose:** To obtain relevant undergraduate programme handbooks, academic regulations, registration information, and academic calendars where publicly available.

**Source 4: UTM Faculty of Computing — Programmes and Student Hub**

URL: https://comp.utm.my/programmes-and-student-hub/

**Purpose:** To identify additional programme and student information that may be useful for expanding the knowledge base.

## Similar to EduAdvisor

Both UniGuide AI and EduAdvisor are document-grounded question-answering systems designed to help students access university information more efficiently. Both can use official documents, semantic retrieval, a large language model, and source citations to produce answers that users can verify.

## Different from EduAdvisor

UniGuide AI focuses on general university FAQs and student services, such as academic calendar dates, course registration procedures, academic regulations, and student resources. EduAdvisor focuses more specifically on academic advising, including course prerequisites, course planning, and graduation requirements.

UniGuide AI will initially prioritise finding and explaining information in official UTM resources rather than making personalised academic recommendations.

## Responsible AI Risks (at least 2)

**Risk 1 — Hallucination and incorrect information:** The assistant may generate incorrect registration requirements, dates, or policies. This could mislead students.

**Mitigation:** Retrieve relevant official passages, provide source citations, evaluate answers against verified reference answers, and decline to answer when the documents do not provide sufficient evidence.

**Risk 2 — Outdated information:** Academic calendars, registration dates, and university policies may change. Answers based on old documents could mislead students.

**Mitigation:** Record document versions and update dates, prioritise current official sources, and display the source date when available. Flag information that has not been verified as current.

**Risk 3 — Unequal answer quality:** Some student questions may be answered less accurately because of ambiguous wording, unfamiliar terminology, or insufficient coverage in the knowledge base.

**Mitigation:** Test the assistant with differently phrased questions, identify gaps in retrieval, use clear fallback messages, and direct students to the relevant official university source when necessary.
