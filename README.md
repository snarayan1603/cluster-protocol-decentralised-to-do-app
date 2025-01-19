# Decentralized To-Do Application

This is a decentralized to-do application built using **React**, **Node.js**, **Express**, and **Solidity**. The application allows users to create, edit, and manage tasks with priority and progress tracking. It also integrates AI to provide productivity advice and supports push notifications.

## Table of Contents

- [File Structure](#file-structure)
- [APIs Used](#apis-used)
- [Installation](#installation)
- [Environment Variables](#environment-variables)
- [Usage](#usage)
- [License](#license)

## File Structure

```
decentralized-todo/
├── backend/
    ├── ai/
│   │   └── ai.js
    ├── credentials/
│   │   └── TaskContract.json
│   ├── middleware/
│   │   └── authMiddleware.js
│   ├── routes/
│   │   └── aiRoutes.js
        └── authRoutes.js
        └── notificationRoutes.js
        └── TaskRoutes.js
│   ├── services/
│   │   └── blockChain.js
│   ├── webpush/
        ├── subscriptions.json
│   │   └── blockChain.js
│   ├── server.js
│   └── package.json
├── blockchain/
│   ├── contracts/
│   │   └── TaskContract.sol
│   ├── scripts/
│   │   └── deploy.js
│   └── hardhat.config.js
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── AddEditTaskDialog.jsx
│   │   │   ├── DashboardComponent.jsx
│   │   │   ├── Header.jsx
│   │   │   ├── Task.jsx
│   │   │   └── Tasks.jsx
        ├── Utility/
│   │   │   ├── auth.js
│   │   │   ├── notification.js
│   │   │   └── utils.js
│   │   ├── App.css
│   │   ├── App.jsx
│   │   ├── Auth.jsx
│   │   ├── main.jsx
│   │   └── service-worker.js
│   ├── public/
│   ├── index.html
│   └── package.json
├── .env
└── README.md
```

## APIs Used

### Backend APIs

- **GET /api/tasks**: Fetch all tasks.
- **GET /api/tasks/count**: Get the count of all tasks.
- **POST /api/tasks/create**: Create a new task.
- **PUT /api/tasks/:id**: Edit an existing task.
- **PATCH /api/tasks/:id/complete**: Mark a task as completed.
- **DELETE /api/tasks/:id**: Delete a task.
- **POST /api/subscribe**: Subscribe to push notifications.
- **POST /api/ai/get-advice**: Get AI productivity advice.
- **POST /api/ai/prioritize-task**: Get prioritized tasks.

## Installation

### Prerequisites

- Node.js
- npm or yarn
- Hardhat
- Metamask (for interacting with the blockchain)

### Steps

1. **Clone the repository**:

   ```sh
   git clone https://github.com/snarayan1603/cluster-protocol-decentralised-to-do-app.git
   cd cluster-protocol-decentralised-to-do-app
   ```

2. **Install dependencies**:

   - Backend:

     ```sh
     cd backend
     npm install
     ```

   - Blockchain:

     ```sh
     cd ../blockchain
     npm install
     ```

   - Frontend:
     ```sh
     cd ../frontend
     npm install
     ```

3. **Set up environment variables**:

   Create a `.env` file in the backend directory and add the following variables:

   ```env
   RPC_URL=<Your_RPC_URL>
   PRIVATE_KEY=<Your_Private_Key>
   CONTRACT_ADDRESS=<Your_Contract_Address>
   VAPID_PUBLIC_KEY=<Your_VAPID_Public_Key>
   VAPID_PRIVATE_KEY=<Your_VAPID_Private_Key>
   ```

   Create a `.env` file in the blockchain directory and add the following variables:

   ```env
   RPC_URL=<Your_RPC_URL>
   PRIVATE_KEY=<Your_Private_Key>
   ```

   Create a `.env` file in the frontend directory and add the following variables:

   ```env
   VAPID_PUBLIC_KEY=<Your_VAPID_Public_Key>
   ```

4. **Deploy the smart contract**:

   ```sh
   cd blockchain
   npx hardhat run --network sepolia/localhost scripts/deploy.js
   ```

5. **Start the backend**:

   ```sh
   cd ../backend
   npm start
   ```

6. **Start the frontend**:
   ```sh
   cd ../frontend
   npm start
   ```

## Environment Variables

- **RPC_URL**: The URL of the Ethereum node.
- **PRIVATE_KEY**: The private key of the Ethereum account.
- **CONTRACT_ADDRESS**: The address of the deployed smart contract.
- **VAPID_PUBLIC_KEY**: The public VAPID key for push notifications.
- **VAPID_PRIVATE_KEY**: The private VAPID key for push notifications.

## Usage

1. **Open the application**:  
   Navigate to `http://localhost:3000` in your web browser.

2. **Create a new task**:  
   Click on "Add Task" and fill in the task details.

3. **Edit a task**:  
   Click on the "Edit" button next to a task and update the task details.

4. **View high-priority tasks**:  
   Navigate to the "Priority Tasks" section to view tasks marked as high priority.

5. **Get AI advice**:  
   Click on the "Get Advice" button to receive productivity advice from the AI.

6. **Receive notifications**:  
   Allow notifications in your browser to receive push notifications.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
