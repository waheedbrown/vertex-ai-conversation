# vertex-ai-conversation
Repository for Vertex AI models

## Summary
* Vertex AI applications are saved in their respective branches
* Manual commits should only be made to the main branch

## Table of Contents
* 1 [Branches](#branches)
  * 1.1 [google-quarterly-earnings](#google-quarterly-earnings)

## 1. Branches
**Vertex AI GitHub Integration Nuances**
* The branches receive commits from Vertex AI via the GitHub Integration API
  * Vertex AI's GitHub Integration API only allows commits to branches, not folders within a branch
  * As well, commits through GitHub Integration delete manually committed files, like README.md
  * The [Vertex AI Search and Conversation](https://cloud.google.com/enterprise-search), GitHub Integration is similar to the one for Dialogflow CX
    * Documentation: [GitHub export/restore](https://cloud.google.com/dialogflow/cx/docs/concept/github)
* Please do not make manual commits to the branches directly
* Manual commits should only be made to the main branch

**Git Subtree Usage**
* Other branches can be manually merged into the main branch, into their respective subtree folder with the same name
  * Example of creating a subtree:
    ```
    git read-tree --prefix=FOLDER-NAME/ -u REMOTE-NAME/BRANCH-NAME
    ```
    ```
    git read-tree --prefix=google-quarterly-earnings/ -u origin/google-quarterly-earnings
    ```
  * Example of updating a subtree:
    ```
    git pull -s subtree REMOTE-NAME BRANCH-NAME
    ```
    ```
    git pull -s subtree origin main google-quarterly-earnings
    ```

  * Documentation: [About Git subtree merges](https://docs.github.com/en/get-started/using-git/about-git-subtree-merges)

### 1.1 [google-quarterly-earnings](https://github.com/waheedbrown/vertex-ai-conversation/tree/google-quarterly-earnings)
This branch contains the Vertex AI Search and Conversation app for a chatbot based on [Alphabet's quarterly earnings reports](https://abc.xyz/investor/)
* Subtree: [google-quarterly-earnings](./google-quarterly-earnings/)
  * Update subtree with the latest commits from the Vertex AI Search and Conversation, GitHub Integration:
    ```
    git pull -s subtree origin main google-quarterly-earnings
    ```