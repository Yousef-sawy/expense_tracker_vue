# Expense and Income Tracker (Vue.js 3)

This is a user-friendly Vue.js 3 application designed to help you effectively manage your personal finances by tracking both your expenses and income. Leveraging your browser's local storage, the application ensures your financial data persists securely within your browser, even after you close it. For enhanced user experience, it integrates the `vue-toastification` library to provide clear and informative pop-up notifications upon successful data entries or when errors occur.

## Key Features

* **Effortless Expense Tracking:** Easily log your expenditures by providing a brief description and the corresponding amount.
* **Simple Income Recording:** Keep track of your earnings by adding a description and the received amount.
* **Comprehensive Transaction History:** View a clear and organized list of all your recorded expenses and income transactions.
* **Persistent Local Storage:** All your financial data is securely stored directly in your browser's local storage, ensuring data retention across sessions.
* **Intuitive User Feedback:** The application utilizes `vue-toastification` to display timely and informative notifications, providing clear feedback for successful actions and error scenarios.

## Recommended Development Environment

* **IDE:** [Visual Studio Code (VSCode)](https://code.visualstudio.com/) is highly recommended for its excellent Vue.js support and development tools.

## Project Setup Instructions

Follow these steps to get the Expense and Income Tracker up and running on your local machine:

1.  **Initialize Your Project:**

    * **If you have the code repository:** Clone it to your local machine using Git:
        ```sh
        git clone <repository_url>
        cd <project_directory>
        ```
    * **If you are starting a new Vue.js 3 project with Vite:**
        ```sh
        npm create vue@latest expense-tracker
        cd expense-tracker
        ```

2.  **Install Dependencies:** Navigate to your project directory in the terminal and install the necessary dependencies using npm:
    ```sh
    npm install
    ```

3.  **Install `vue-toastification`:** Add the `vue-toastification` library to your project:
    ```sh
    npm install vue-toastification --save
    ```

## Development Workflow

### Compile and Hot-Reload for Development

To start the development server with hot-reloading, which automatically updates the browser when you make changes to the code, run the following command:

```sh
npm run dev
```
![mainPage](https://github.com/user-attachments/assets/b99896c8-e598-4a60-a471-e86461b3f101)
