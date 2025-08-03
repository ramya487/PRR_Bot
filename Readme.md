<p align="center">
<img height="40" alt="horizontal-logo-gradient-blue-atlassian" src="https://github.com/user-attachments/assets/dcf5ef2d-ecef-420b-8151-cad1849d2144" /> &nbsp;
<img height="45" alt="logo-gradient-blue-bitbucket" src="https://github.com/user-attachments/assets/b2b47870-cc29-4845-a413-c99534efd3ee" />
</p>

# <p align="center">PULL REQUEST REVIEWER BOT</p>

PRR Bot is an application that is built using atlassian forge platform. It seamlessly integrates with bitbucket, and assists in code review process by analyzing pull requests and providing detailed feedback on code quality, potential issues, and optimizations. It helps developers identify minor flaws, improve efficiency, and maintain best coding practices, reducing manual review effort and thus ensuring higher code standards

<section>
  <a href="https://youtu.be/17qtKcrNx4c" target="_blank"><img src="https://github.com/user-attachments/assets/7182222a-3bb2-47e5-ad74-c22c478664b1" alt="demovideo" height="40" /></a>
</section>

## Features

#### 1. AI-Powered Analysis

Using LLM, the application evaluates the pull request’s code, detecting minor flaws, suggesting performance improvements. The AI provides contextual and actionable suggestions, reducing the time needed for manual code reviews.

#### 2. Bitbucket Integration

Seamlessly integrates within the Bitbucket environment, allowing developers to review and refine their code without leaving their workflow. The app works directly within Bitbucket’s UI.

#### 3. Inline PR Comments

Once the review is complete, the application can allows to add AI-generated feedback as comments directly within the pull request. This allows developers and reviewers to see suggestions alongside the relevant code changes, making it easier to address issues and apply improvements

## Technologies Used

#### 1. Forge

Forge is a cloud based, serverless app development platform for atlassian products. This has been used to integrate with Bitbucket's UI and interact with the APIs. **Forge UI Kit** is a **React based** framework that provides pre-built UI components to embed the app seamlessly within the Bitbucket interface.

#### 2. Bitbucket cloud REST API

Bitbucket Cloud REST API has been utilized via **Forge Product Fetch API** , to fetch pull request data, retrieve code changes, and post comments back into the pull request, ensuring seamless integration within Bitbucket environment.

#### 3. LLM and FastAPI

This project uses Google ```gemini-1.5-pro``` model to for code analyzation and generate efficient comments. FastAPI has been utilized to construct the backend which typically is used to interact with the LLM and send the response to the frontend

#### 4. Langchain and LangServe

Langchain has been used to interact with the LLM, specifically the the module ```langchain-google-genai``` that is utilized to send requests to Gemini model. Further it was also utilized to generate accurate prompts, and format the output from the LLM, according to what is required by the application

LangServe has been used to deploy the LLM chains as a REST API

## Architecture

![forge (3)](https://github.com/user-attachments/assets/d974bd03-a7ce-473a-9075-7339643056a9)

#### 1. Fetch Open Pull Requests

The Forge Custom UI invokes to the Forge Product Fetch API which makes a request to the Bitbucket Cloud REST API which fetches the open pull requests for the repository

#### 2. Fetch File Contents

Next the files which have undergone a change or have been added or removed is determined from the pull request diff. The contents of the file as of the latest commit in the pull request is fetched

#### 3. LLM Review

The fetched file contents is then sent to the FastAPI backend which then sends a request to Gemini for review. The suggested comments from the LLM is then sent to the frontend

#### 4. Add Comments To Pull Reqeust

The suggested comments from the LLM is then displayed to the user and could be further added directly as comments to the pull request alongside the revelant code changes
