# PULL REQUEST REVIEWER BOT

PRR Bot is an application that is built using atlassian forge platform. It seamlessly integrates with bitbucket, and assists in code review process by analyzing pull requests and providing detailed feedback on code quality, potential issues, and optimizations. It helps developers identify minor flaws, improve efficiency, and maintain best coding practices, reducing manual review effort and thus ensuring higher code standards

## Features

### 1. Automated code review

It assists in code review process, analysing for potential flaws, optimizations and best practises, thus eliminating the need for manual code review

### 2. AI-Powered Analysis

Using an advanced LLM, the application evaluates the pull request’s code, detecting minor flaws, suggesting performance improvements, and ensuring adherence to best coding practices. The AI provides contextual and actionable suggestions, reducing the time needed for manual code reviews.

### 3. Bitbucket Integration

Seamlessly integrates within the Bitbucket environment, allowing developers to review and refine their code without leaving their workflow. The app works directly within Bitbucket’s UI, making the review process smoother and more efficient.

### 4. Inline PR Comments

Once the review is complete, the application can allows to add AI-generated feedback as comments directly within the pull request. This allows developers and reviewers to see suggestions alongside the relevant code changes, making it easier to address issues and apply improvements

## Technologies Used

### 1. Forge

Forge is a cloud based, serverless app development platform for atlassian products. This has been used to integrate with Bitbucket's UI and interact with the APIs. **Forge UI Kit** is a **React based** framework that provides pre-built UI components to embed the app seamlessly within the Bitbucket interface.

### 2. Bitbucket cloud REST API

Bitbucket Cloud REST API has been utilized via **Forge Product Fetch API** , to fetch pull request data, retrieve code changes, and post comments back into the pull request, ensuring seamless integration within Bitbucket environment.

### 3. LLM and FastAPI

This project uses Google ```gemini-1.5-pro``` model to for code analyzation and generate efficient comments. FastAPI has been utilized to construct the backend which typically is used to interact with the LLM and send the response to the frontend

### 4. Langchain and LangServe

Langchain has been used to interact with the LLM, specifically the the module ```langchain-google-genai``` that is utilized to send requests to Gemini model. Further it was also utilized to generate accurate prompts, and format the output from the LLM, according to what is required by the application

LangServe has been used to deploy the LLM chains as a REST API