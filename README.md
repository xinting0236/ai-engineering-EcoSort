# EcoSort — AI-Powered Waste Classification and Recycling Assistant

> Helps users identify common waste materials from images and obtain recycling and disposal guidance grounded in public waste-management documents.

## Problem Statement

People may find it difficult to identify waste materials and determine how to dispose of them correctly. Waste-management information is distributed across different public documents, making it time-consuming to find relevant guidance. EcoSort AI combines image classification and Retrieval-Augmented Generation (RAG) to classify common waste materials and provide document-grounded disposal guidance with source citations.

## Evidence of the Problem

- Malaysia's national recycling rate was **37.9% in 2024**, according to official data compiled from KPKT administrative records. Source: [Malaysia SDG Indicator 12.5.1 — Recycling Rate](https://data.gov.my/data-catalogue/sdg_12-5-1)
- Global municipal solid waste is projected to increase from **2.1 billion tonnes in 2023 to 3.8 billion tonnes by 2050**. Source: [UNEP — Global Waste Management Outlook 2024](https://www.unep.org/en/publications/report/global-waste-management-outlook-2024)

## Initial Related Work / Existing Approaches

- **TrashNet — Classification of Trash for Recyclability Status:** Provides an image dataset for six waste categories: glass, paper, cardboard, plastic, metal, and trash. Limitation: images were captured in relatively controlled settings and do not cover all real-world waste conditions. Source: [TrashNet GitHub Repository](https://github.com/garythung/trashnet)
- **Deep Convolutional Neural Networks Object Detector for Real-Time Waste Identification:** Explores deep learning for waste identification. Limitation: identifying waste does not automatically provide location-specific disposal instructions. Source: [Applied Sciences, 2020](https://www.mdpi.com/2076-3417/10/20/7301)
- **MobileNetV2 — Inverted Residuals and Linear Bottlenecks:** Presents an efficient deep-learning architecture suitable for image classification. Limitation: MobileNetV2 is a general-purpose architecture and does not independently provide waste-management guidance. Source: [Sandler et al., CVPR 2018](https://openaccess.thecvf.com/content_cvpr_2018/html/Sandler_MobileNetV2_Inverted_Residuals_CVPR_2018_paper.html)

## Engineering Gap / Limitation

Existing image-classification approaches can identify waste categories but may not explain how to dispose of the identified material. Public waste-management information can also be difficult to search across multiple documents. EcoSort AI addresses this gap by integrating image classification with a RAG assistant that retrieves relevant information and provides answers with source citations. The system will distinguish material identification from actual recycling-facility acceptance, which may depend on local rules.

## Project Objectives

- **O1:** To develop a waste image-classification model using MobileNetV2 and the TrashNet dataset.
- **O2:** To develop a RAG-based assistant that retrieves information from public waste-management documents and provides disposal guidance with source citations.
- **O3:** To integrate the image classifier and RAG assistant into a web application and evaluate classification performance, retrieval relevance, answer groundedness, citation correctness, and response latency.

## Target Users

- Households and members of the public.
- Students and educators learning about waste separation.
- Environmentally conscious users seeking waste-disposal guidance.

The initial scope focuses on common household waste and publicly available Malaysian waste-management guidance.

## Data Sources

- **TrashNet image dataset** — waste images for training and evaluating the image-classification model.  
  URL: https://github.com/garythung/trashnet
- **Guidelines for Source Separation of Municipal Solid Wastes** — public guidance on waste separation.  
  URL: https://jpspn.kpkt.gov.my/jpspn/resources/Images%20JPSPN/Sumber%20Rujukan/Garis%20Panduan%20Teknikal/Guidelines_for_Source_Separation_of_Municipal_Solid_Wastes.pdf
- **SWCorp Household Solid Waste Regulations** — information about household solid-waste regulations.  
  URL: https://www.swcorp.gov.my/en/household-solid-waste-regulations/
- **UNEP Global Waste Management Outlook 2024** — global waste-management information and statistics.  
  URL: https://www.unep.org/en/publications/report/global-waste-management-outlook-2024

## Weekly Progress

| Week | Focus | Deliverable | Status |
|---|---|---|---|
| W1 | System map and project scope | README.md and initial documentation | ✅ Completed |
