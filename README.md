# 🏋️‍♂️ Workout Timer App

![Workout Timer Screenshot](./screenshots/app-screenshot.png)

A sleek, dynamic React application designed to calculate total workout durations based on exercise types, sets, and performance speed. This app features real-time updates, audio feedback, and time-of-day awareness.

## 📖 Overview
The Workout Timer helps fitness enthusiasts plan their sessions accurately. It doesn't just calculate movements; it factors in rest periods and individual pacing to give a realistic completion time.

---

## ✨ Key Features
* **Dynamic Workout Logic**: The available exercises and their counts automatically adjust based on whether it is morning (AM) or evening (PM).
* **Real-Time Calculations**: Uses a specialized formula to update the total duration instantly whenever inputs like sets, speed, or break lengths change.
* **Audio Feedback**: Plays a "click" sound notification upon time updates to enhance user interaction (can be toggled on/off).
* **Live Clock**: Displays a continuously updating date and time formatted for clarity.
* **Interactive Controls**: Features range sliders for precise input and manual increment/decrement buttons for quick adjustments.
* **Browser Integration**: Dynamically updates the browser tab title to reflect the current workout's exercise count.

---

## 🛠️ Technical Stack
* **React (Hooks)**: 
    * `useState`: Manages state for workout parameters, time, and sound settings.
    * `useEffect`: Synchronizes side effects like the 1-second interval timer, audio playback, and DOM title updates.
    * `useMemo` & `memo`: Optimizes performance by memoizing complex objects and preventing unnecessary re-renders of child components.
* **CSS3**: Modern styling using Flexbox for centering, CSS Gradients for vibrant UI, and responsive units (`rem`).
* **Internationalization API**: Utilizes `Intl.DateTimeFormat` for professional, locale-aware time formatting.

---

## 📂 Project Structure
* `App.js`: The main hub managing global time state and dynamic workout definitions.
* `Calculator.js`: The core engine handling duration logic, formulas, and input forms.
* `ToggleSounds.js`: A specialized button component for managing audio state.
* `index.css`: Contains all visual styling and layout rules.
* `ClickSound.m4a`: The audio asset used for user feedback.

---

## 🚀 Getting Started

### Prerequisites
* Node.js (latest stable version)
* npm or yarn

### Installation
1.  **Clone the repository**:
    ```bash
    git clone [https://github.com/your-username/workout-timer.git](https://github.com/your-username/workout-timer.git)
    ```
2.  **Navigate to the project directory**:
    ```bash
    cd workout-timer
    ```
3.  **Install dependencies**:
    ```bash
    npm install
    ```
4.  **Run the app**:
    ```bash
    npm start
    ```

---

## 📝 Technical Implementation Details
* **The Formula**: Duration is calculated using:
    $$Duration = \frac{(Exercises \times Sets \times Speed) + ((Sets - 1) \times Break \times 60)}{60}$$
   
* **Performance Optimization**: The `Calculator` component is wrapped in `memo` to ensure it only updates when its specific props (`workouts` or `allowSound`) change.
* **Cleanup**: The `App` component properly clears the `setInterval` on unmount to prevent memory leaks.

---
