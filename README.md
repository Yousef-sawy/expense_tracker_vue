# Expense and Income Tracker (Vue.js)

This is a simple Vue.js 3 application that allows you to track your expenses and income. The application saves all data locally using your browser's local storage. It also utilizes the `vue-toastification` library to display informative pop-up notifications upon data entry or when errors occur.

## Features

* **Add Expenses:** Easily record your expenditures with descriptions and amounts.
* **Add Income:** Track your earnings with descriptions and amounts.
* **View Transactions:** See a clear list of all your recorded expenses and income.
* **Local Storage:** All data is saved directly in your browser's local storage, ensuring your information persists even after closing the browser.
* **User-Friendly Notifications:** Uses `vue-toastification` to provide clear and concise feedback for successful actions and error scenarios.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Customize Configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

1.  **Clone the repository (if applicable) or create a new Vue project:**
    ```sh
    # If starting from scratch using Vite:
    npm create vue@latest expense-tracker
    cd expense-tracker
    ```

2.  **Install dependencies:**
    ```sh
    npm install
    ```

3.  **Install `vue-toastification`:**
    ```sh
    npm install vue-toastification --save
    ```

### Compile and Hot-Reload for Development

```sh
npm run dev
