## Project Name

AI-Powered Waste Management and Recycling Assistant

## Domain

Artificial Intelligence / Computer Vision / Sustainable Waste Management / Natural Language Processing

## Problem Statement

People may find it difficult to identify the correct waste category and determine how to dispose of household waste responsibly. Waste-management information is available through government guidelines and other public resources, but users may need to consult different sources to find relevant instructions.

This project proposes a web-based AI assistant that classifies waste from uploaded images using a trained MobileNetV2 image-classification model. It also uses Retrieval-Augmented Generation (RAG) to retrieve relevant information from public waste-management documents and generate answers with source citations. The system aims to help users identify common waste categories and access relevant disposal guidance.

## Evidence of the Problem

**Evidence 1:** Malaysia's national recycling rate reached 37.9% in 2024, according to data compiled from government administrative records. The Malaysian government has also promoted waste separation at source and recycling initiatives. This supports the relevance of developing tools that help people access waste-management information and identify recyclable materials.

**Source / citation:** Department of Statistics Malaysia and Ministry of Housing and Local Government, National Recycling Rate dataset.  
https://data.gov.my/data-catalogue/sdg_12-5-1

**Evidence 2:** The United Nations Environment Programme's *Global Waste Management Outlook 2024* estimates that global municipal solid waste generation could increase from 2.1 billion tonnes in 2023 to 3.8 billion tonnes by 2050. The report highlights the importance of improving waste prevention and management.

**Source / citation:** United Nations Environment Programme (UNEP), *Global Waste Management Outlook 2024*.  
https://www.unep.org/en/publications/report/global-waste-management-outlook-2024

## Initial Related Work (at least 3)

### Study / solution 1: Classification of Trash for Recyclability Status — TrashNet

**Source / citation:** Thung, G. and Yang, M. (2016). *Classification of Trash for Recyclability Status*. Stanford CS229 project report.  
Dataset and project repository: https://github.com/garythung/trashnet  
Project report: https://cs229.stanford.edu/proj2016/report/ThungYang-ClassificationOfTrashForRecyclabilityStatus-report.pdf

**Key limitation:** The dataset contains 2,527 images across six classes: glass, paper, cardboard, plastic, metal and trash. Images were captured under relatively controlled backgrounds and lighting conditions. Therefore, a model trained on this dataset may not perform equally well on real-world images with cluttered backgrounds, different lighting or unfamiliar objects. The dataset also does not provide Malaysian disposal rules.

### Study / solution 2: Deep Convolutional Neural Networks Object Detector for Real-Time Waste Identification

**Source / citation:** *Applied Sciences*, 2020.  
https://www.mdpi.com/2076-3417/10/20/7301

**Key limitation:** The study investigates deep-learning-based waste identification using image data. However, waste identification alone does not provide users with source-supported, location-relevant disposal instructions. My project will combine image classification with a document-grounded RAG assistant.

### Study / solution 3: MobileNetV2 — Inverted Residuals and Linear Bottlenecks

**Source / citation:** Sandler, M., Howard, A., Zhu, M., Zhmoginov, A. and Chen, L.-C. (2018). *MobileNetV2: Inverted Residuals and Linear Bottlenecks*. Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), pp. 4510–4520.  
https://openaccess.thecvf.com/content_cvpr_2018/html/Sandler_MobileNetV2_Inverted_Residuals_CVPR_2018_paper.html

**Key limitation:** MobileNetV2 is a general-purpose vision architecture rather than a complete waste-management solution. It does not independently provide recycling instructions or verify whether a particular recycling facility accepts an item. Its performance for this project must be evaluated on the selected waste-classification dataset.

## Engineering Gap / Limitation

Existing waste-classification models can identify common waste categories from images, while public documents provide waste-management and recycling guidance. However, these functions are often separate. The proposed system integrates image classification with RAG so that users can upload a waste image, obtain a predicted category, and retrieve relevant disposal guidance with supporting source citations in one web application.

The system will also communicate uncertainty when an image cannot be classified confidently or when the available documents do not provide enough information. A predicted material category will not automatically be treated as proof that the item is accepted by every recycling centre.

## Initial Project Objectives (2–3)

**O1:** To design and develop a waste-image classification model using transfer learning with MobileNetV2 to classify common waste categories based on the TrashNet dataset.

**O2:** To develop a web-based RAG assistant that retrieves relevant information from public waste-management documents and generates disposal guidance with source citations.

**O3:** To integrate the image-classification model and RAG assistant into a single web application and evaluate the system using classification performance, retrieval relevance, answer groundedness, citation correctness and response time.

## Target Users

- Members of the public who want to identify common household waste items.
- Students and households seeking accessible recycling and waste-disposal information.
- Environmentally conscious users who want to understand waste categories and find relevant disposal guidance.

The initial prototype will focus on common household waste categories represented in TrashNet and publicly documented guidance relevant to Malaysia.

## Data Sources (at least 2)

**Source 1:** TrashNet image-classification dataset — 2,527 images in six categories: glass, paper, cardboard, plastic, metal and trash. Used to train and evaluate the image-classification model.  
URL: https://github.com/garythung/trashnet

**Source 2:** Guidelines for Source Separation of Municipal Solid Wastes — published by Malaysia's National Solid Waste Management Department (JPSPN). Used as a source of waste-separation guidance. Check the document's publication date and validate guidance against current information.  
URL: https://jpspn.kpkt.gov.my/jpspn/resources/Images%20JPSPN/Sumber%20Rujukan/Garis%20Panduan%20Teknikal/Guidelines_for_Source_Separation_of_Municipal_Solid_Wastes.pdf

**Source 3:** Household Solid Waste Regulations — SWCorp Malaysia. Used for relevant Malaysian regulatory information.  
URL: https://www.swcorp.gov.my/en/household-solid-waste-regulations/

**Source 4:** Global Waste Management Outlook 2024 — United Nations Environment Programme (UNEP). Used for background information on global waste-management challenges and principles.  
URL: https://www.unep.org/en/publications/report/global-waste-management-outlook-2024

## Similar to EduAdvisor

Both projects use AI to help users access useful information through a web application. They retrieve information from existing documents and generate responses based on relevant sources. Both require appropriate evaluation and safeguards to reduce unsupported AI-generated answers.

## Different from EduAdvisor

EduAdvisor focuses on academic advising and answering questions about university information. My project focuses on waste management and recycling. It combines computer vision to classify uploaded waste images with RAG to retrieve and explain relevant waste-disposal guidance. It also evaluates image-classification performance in addition to retrieval and answer quality.

## Responsible AI Risks (at least 2)

**Risk 1 — Incorrect image classification:** The model may misclassify an item, particularly when images have poor lighting, cluttered backgrounds or objects that are not represented in TrashNet. The application should display the predicted category and confidence where appropriate, and ask users to upload a clearer image when confidence is low.

**Risk 2 — Hallucination or unsupported disposal advice:** The RAG assistant may generate incorrect recycling instructions or provide a citation that does not support its answer. The system should retrieve relevant passages, provide source citations, evaluate citation correctness and state when the available documents cannot answer a question.

**Risk 3 — Misleading local recycling guidance:** A material may be recyclable in principle but not accepted by a particular collection centre. The system must distinguish material classification from local acceptance rules and avoid claiming that a facility accepts an item unless a reliable source confirms it.


