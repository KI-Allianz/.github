# KI-Allianz Baden-Württemberg
with our partners we are developing the AI Data Platform (KI-Datenplattform)

The **AI Data Platform** is an open, interoperable infrastructure developed by the **KI Allianz Baden-Württemberg**.  
Its goal: make **high-quality datasets**, **AI models**, and **compute resources** easily accessible to companies, researchers, and public institutions.

<img width="60%" alt="KI-Allianz data plattform" src="https://github.com/user-attachments/assets/68405841-ef2e-49b2-90ae-e50aafa10edc" />


## 🌐 What the Platform Aims to Provide
- A **metadata-based catalog** for datasets and AI models
- A **cross-sectorial federation platform for data spaces** containing domain specific data
- **Quality assurance tools** for data preparation and annotation  
- Seemless workflows towards **Cloud and HPC resources** for training and experimentation with data 
- Built-in **legal & ethical compliance** for safe data use  

## 💡 Why It Matters
Many organizations — especially SMEs — lack structured data, annotation tools, or legal clarity.  
The AI Data Platform removes these barriers, helping teams build trustworthy and production-ready AI solutions faster.

## 🤝 Participate
Early adopters can:
- Test platform features
- Provide feedback within our User Forum
- Co-shape standards and use cases
- Develop together
- Fork us to run your own data space catalog

What you can do soon:
- Efficiently find high value, AI-ready data sets across sectorial domains
- Federate your data catalog within the AI Allianz to offer data and AI models to customers
- Use our catalogs to federate with your internal knowledge management systems

## Core Platform Components

The power of the AI Data Platform lies in its set of modular, specialized components that work together to create a seamless user experience. This section explores the cornerstone releases that form the foundation of this new ecosystem: 
- a reimagined frontend for an intuitive portal experience,
- a novel AI powerered search and interactions for superior discoverability,
- automated data quality services to ensure trustworthy AI,
- and a suite of data integration tools to connect critical sectoral data spaces and your AI workflows

We are building our AI Data Platform on top of the field-proven [piveau](https://piveau.com) ecosystem developed by Fraunhofer FOKUS that again builds on the widely adopted DCAT standard.  

### The New Frontend: Piveau.nextjs — A Modern Data Portal Experience
🔗 https://github.com/KI-Allianz/piveau.nextjs 

At the forefront of the platform is Piveau.nextjs, a new modern web interface that serves as the primary gateway for users. This component reimagines the Piveau data portal experience, focusing on discoverability, accessibility, and performance.

Its key features include:

* Full Feature Parity: The new frontend retains all core functionalities of the original Piveau platform, including robust dataset search, advanced filtering, sorting, and data visualization.
* Enhanced User Experience: It introduces new capabilities designed for modern data workflows. Users can now save and manage User Favorites directly in their browser and navigate to dedicated detail pages for AI models via AI Model Routing.
* Optimized Performance: Built on a modern technology stack featuring Next.js 15, the interface leverages server-side rendering (SSR) to deliver superior performance. This ensures that valuable datasets and models are not only fast to access for users but are highly discoverable by external search engines, maximizing their reach and impact.

### Smarter Search — Find What You Mean, Not Just What You Type
🔗 https://github.com/KI-Allianz/DCAT-metadata-assistant

We have integrated a DCAT-aware Chat-Agent that can answer complex questions about data sets in the plattform using the structured Meta Data available.

<img width="50%" alt="Meta Data Chat" src="https://github.com/user-attachments/assets/93a56367-d2c5-4240-9cd0-53a3d10a18c9" />


A significant upgrade to the platform's discovery engine comes with the Semantic-Hub-Search component. This innovation enhances the existing lexical (keyword-based) search with a powerful semantic function, creating a state-of-the-art hybrid system. Instead of merely matching keywords, the search now understands the conceptual meaning behind a user's query.

The primary benefits of this semantic approach are:

* Conceptual Understanding: The engine recognizes thematic relationships between terms. For example, a search for "Bahn" (train) will also return relevant results for "Schienenverkehr" (rail transport), significantly improving the breadth of discovery.
* Improved Accuracy: By understanding context and intent, the search delivers more relevant and precise results, reducing the time needed to find the right data.
* Cross-Lingual Capabilities: The underlying technology supports searches across different languages, breaking down barriers for a more inclusive data ecosystem.

This advanced functionality is powered by word embeddings generated via a configurable Ollama-based service. Search requests trigger a vector search in Elasticsearch, and the results are then intelligently combined with a classical lexical full-text search using a "rescore-query" to deliver the best of both worlds.

### Data Quality Services — Ensuring Trustworthy and Reliable AI
🔗 https://github.com/KI-Allianz/DataQualityServices

The principle that data quality determines AI success is a core tenet of the platform. A suite of automated services has been released to turn raw data into quality-assured assets, laying the foundation for trustworthy and reliable AI applications. These tools are accessible through a user-friendly, wizard-based interface that supports CSV/XLSX uploads and can publish cleaned results directly back to the Piveau Hub.

<img width="50%" alt="Data Quality Services" src="https://github.com/user-attachments/assets/78d9d03b-820f-40aa-848d-259ca882482b" />

The available services are detailed below:

Service Name	Core Function and Impact
Data Quality AI Service	This multi-step pipeline transforms raw data into a clean, structured, and compliant format. It automates critical tasks including:<br><ul><li>Automated Feature Type Inference: Correctly classifies data columns.</li><li>Personal Data Detection: Flags sensitive information for privacy compliance.</li><li>Automated Data Imputation: Intelligently handles missing values.</li><li>Anomaly Detection: Identifies unusual patterns that may indicate errors.</li></ul>
Outlier Detection (XGBOD)	This service utilizes a pre-trained, machine learning-based model (XGBOD) to specifically identify and isolate outliers in tabular data. By flagging anomalous data points, it helps users refine datasets, reduce noise, and ultimately improve the performance and reliability of their AI models.

### A Data Integration Hub — Connecting Sectoral Data Spaces

A key strategic goal of the AI Data Platform is to enable cross-sector innovation by bridging industry-specific data spaces. A collection of "harvesters" and tools has been developed to connect the platform with critical sectors, making siloed data findable and accessible in line with major European data initiatives.

Key integration tools in this release include:

#### Excel2DCAT Importer ####
🔗 https://github.com/KI-Allianz/piveau-excel-importer 

A low entry barrier tool for importing AI assets into our data catalogs straight from Microsoft Excel template document
#### Hugging Face to DCAT
🔗 https://github.com/KI-Allianz/hf2dcat 

Import existing AI-ready data sets and AI models straight from the current definite source and convert them into the standardized DCAT format for better interoperability with data management workflows and other data spaces
#### AAS2DCAT Tool (Industry 4.0)
🔗 https://github.com/KI-Allianz/aas2dcat 

This PyQt5-based desktop application actively bridges the world of manufacturing with the platform. It maps Asset Administration Shell (AAS) models from FA³ST or BaSyx repositories into DCAT-AP datasets, enabling Industry 4.0 data to be published and discovered in alignment with Manufacturing-X concepts.
#### mds2hdcat (Health)
🔗 https://github.com/KI-Allianz/mds2hdcat

A powerful command-line tool designed to prepare health data for broader use. It converts metadata records from the NFDI4Health standard into the Health DCAT-AP standard, making them ready for inclusion in catalogues for the European Health Data Space (EHDS).
#### FROST-Server DCAT Plugin (IoT/Smart City)
🔗 https://github.com/KI-Allianz/FROST-Server

An essential extension for IoT applications that promotes urban resilience. It enables SensorThings API data streams to be exported as a DCAT-AP compliant catalogue, making real-time sensor data from Smart City and industrial domains findable and reusable.

While these core components provide a powerful, ready-to-use platform, their true potential is unlocked by the developer community. To that end, we've equipped developers with the following tools to build the next generation of AI applications.

## For Developers: Tools & Libraries to Build With

For developers, data scientists, and engineers who wish to programmatically interact with the platform's assets, the python-dcat-ap-hub library offers a streamlined and efficient solution. This Python library is designed for easy downloading and loading of datasets and models directly from the platform's catalog.

<img width="30%"  alt="Integration DCAT-AP hub into data plattform" src="https://github.com/user-attachments/assets/f11f13ce-85cc-4eee-a398-260659cb3d02" />

Its primary functions include:

* Loading Datasets: The library can download and load any dataset whose metadata is provided in the DCAT-AP (JSON-LD) format, simplifying the process of integrating data into custom scripts and applications.
* Loading Huggingface Models: It includes a specialized function to directly load Huggingface models that are referenced in the platform's catalog, providing seamless access to pre-trained models for AI development.
