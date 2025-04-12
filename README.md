Let me check all the files and provide a comprehensive guide on how to use and run the application:

Read file: README.md

Read file: package.json

Read file: data.json

Ran tool
Based on the available information, here's a comprehensive guide on how to use and run the Sentence Builder application:

# Sentence Builder - User Guide

## Introduction
Sentence Builder is an interactive sentence construction tool where users fill in blanks with appropriate words to complete sentences. It features a timer, multiple-choice options, and detailed feedback on performance.

## Prerequisites
- Node.js (v14 or higher)
- npm (Node Package Manager)

## Installation Steps

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd sentence-builder
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```
   This will install all required packages including React, TypeScript, Tailwind CSS, and JSON Server.

## Running the Application

The application requires two servers to run simultaneously:

### 1. Start the JSON Server (Backend)
```bash
npm run json-server
```
This will start JSON Server on port 3001, which serves the question data from the data.json file. The server endpoints are:
- http://localhost:3001/data - Main data endpoint
- http://localhost:3001/questions - Questions endpoint
- http://localhost:3001/status - Status endpoint
- http://localhost:3001/message - Message endpoint
- http://localhost:3001/activity - Activity endpoint

### 2. Start the Development Server (Frontend)
```bash
npm run dev
```
This will start the Vite development server, typically on port 5173. Open your browser and navigate to:
```
http://localhost:5173
```

If port 5173 is already in use, Vite will automatically use another port (like 5174 or 5175).

## How to Use the Application

### Start Screen
1. When you first load the application, you'll see the Start Screen with instructions.
2. Click the "Start Quiz" button to begin.

### Question Screen
1. Each question displays a sentence with blanks marked by underscores.
2. You'll see four word options below the sentence.
3. Click on a word to place it in the first available blank.
4. To remove a word from a blank, click on the filled blank.
5. A 30-second timer counts down for each question.
6. Once all blanks are filled, the "Next" button becomes active.
7. Click "Next" to submit your answer and move to the next question.
8. If the timer runs out, the application automatically submits your answer and moves to the next question.

### Results Screen
1. After completing all questions (or if time runs out on the final question), you'll see the Results Screen.
2. The screen displays:
   - Your overall score as a percentage
   - Number of correct answers out of total questions
   - A detailed breakdown of each question showing:
     - Your answers (correct in green, incorrect in red)
     - The correct answers for any mistakes
3. Click "Try Again" to restart the quiz.

## Project Structure

- `/src` - Source code
  - `/components` - React components for the UI
  - `/lib` - Utility functions
  - `/types` - TypeScript interface definitions
  - `/pages` - Page components
  - `/assets` - Static assets
- `data.json` - Question data for JSON Server
- Configuration files for Tailwind CSS, TypeScript, and Vite

## Building for Production

To create a production build:
```bash
npm run build
```

This generates optimized files in the `/dist` directory, which can be deployed to hosting services like Vercel, Netlify, or GitHub Pages.

## Troubleshooting

1. **JSON Server Port Already in Use**
   - If you see `Error: listen EADDRINUSE: address already in use :::3001`, it means port 3001 is already being used.
   - Find and close the process using port 3001 or modify the port in package.json.

2. **Failed to Load Questions**
   - Ensure JSON Server is running properly on port 3001.
   - Check that data.json is properly formatted.
   - Verify the fetch URL in the App.tsx file points to the correct endpoint (http://localhost:3001/data).

3. **Development Server Issues**
   - If the dev server won't start, try clearing the node_modules folder and reinstalling dependencies:
     ```bash
     rm -rf node_modules
     npm install
     ```

This Sentence Builder application is a responsive, interactive tool that works across different screen sizes and provides an engaging experience for users to practice sentence construction.
