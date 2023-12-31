# PS Info Assistant Features

* [Document Pre-Processing](#document-pre-processing)
* [User Experience](#user-experience)
  * [Having a conversation with your Private Data](#having-a-conversation-with-your-data)
  * [Ask your data](#ask-your-data)
  * [Analysis Panel](#analysis-panel)
  * [Manage Content](#manage-content)
    * [Uploading files](#uploading-files)
    * [View upload status](#view-upload-status)
* [Developer Settings](#developer-settings)
  * [Configuring your own language ENV file]()
  * [Debugging Functions](#debugging-functions)
  * [Build pipeline for sandbox environment](#build-pipeline-for-sandbox)

---

## Document Pre-processing

The Information Assistant Accelerator pre-processes certain document types to allow better understanding of large complex documents. Currently we apply special processing on:

* PDF
* HTML
* DOCX

For more details on how we process each document type click on on the document type in the list above.

We also log the status of the pre-processing in Azure Cosmos DB. View our [Status Logging](../../functions/shared_code/status_log.md) page for more details.

## User Experience

The end user leverages the web interface as the primary method to engage with the IA Accelerator, and the Azure OpenAI service. The user interface is very similar to that of the OpenAI ChatGPT interface, though it provides different and additional functionality which is outlined below.

### Having a conversation with your data

When you engage with IA Accelerator in the "Chat" method, the system maintains a history for your conversation and will be able to understand the context of your questions from one question to the next.

> You may activate the Chat engagement pattern by choosing the "Chat" link at the top of the page
> ![Chat Link](../images/chat-interface.jpg)

### Ask your data

When you engage with IA Accelerator in the "Ask a question" method, the system does not maintain a history for your conversation. Each question will be treated with on its own as a new and unique query.

> You may activate the **Ask a question** engagement pattern by choosing the "Chat" link at the top of the page
> ![Chat Link](../images/ask-a-question-interface.jpg)

### Analysis Panel

The Analysis Panel in the UX allows the user to explore three details about the answer to their question:

* Thought Process
* Supporting Content
* [Citations](./ux_analysispanel.md#citations)

View the details of the [Analysis Panel](./ux_analysispanel.md) feature or you can click on each section to get more specifics of that detail tab.

### Manage Content

When you engage with IA Accelerator in the "Manage Content" method, the system allows you to add new content and see the status of processing for content previously loaded into the IA Accelerator.

> You may activate the Manage Content engagement pattern by choosing the "Manage Content" link at the top of the page
> ![Manage Content Link](../images/manage-content-interface.png)

#### Uploading files

You can upload documents in the [supported formats listed above](#document-pre-processing) through the user interface. To do so:

> 1. Click on the Manage Content link in the top of the interface
> ![Manage Content](../images/manage-content-interface.png)
> 1. Then click on the "Upload files" tab.
> ![Upload Link](../images/upload-files-link.png)
> 1. Drag files to the user interface, or click to open a browse window
> ![Upload Link Drag and Drop](../images/upload-files-drag-drop.jpg)

#### View upload status

You can view the status up files that have been uploaded to the system through the user interface. To do so:

> 1. Click on the Manage Content link in the top of the interface
> ![Manage Content](../images/manage-content-interface.png)
> 1. Then click on the "Upload Status" tab.
> ![Upload Status Link](../images/view-upload-status-link.png)
> 1. Select options and **Refresh** the view. The options defaults to *4 hours* Timespan and *All* File Status. 
> ![Upload Status Options and Refresh Links](../images/view-upload-status-options-and-refresh.png)

## Developer Settings

### Configuring your own language ENV file

At deployment time, you can alter the behavior of the IA Accelerator to use a language of your choosing across it's Azure Cognitive Search and Azure OpenAI prompting. See [Configuring your own language ENV file](./configuring_language_env_files.md) more information.

### Debugging functions

Check out how to [Debug the Azure functions locally in VSCode](https://learn.microsoft.com/azure/cognitive-services/openai/overview)

### Build pipeline for Sandbox

Setting up a pipeline to deploy a new Sandbox environment requires some manual configuration. Review the details of the [Procedure to setup sandbox environment](setting_up_sandbox_environment.md) here.
