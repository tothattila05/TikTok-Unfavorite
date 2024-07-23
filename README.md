# TikTok Unfavoriter

A script designed to automate the removal of videos from your favorites on TikTok. This script scrolls through your TikTok feed and clicks the "unfavorite" button on videos that are currently favorited.

## Features
- Automatically scrolls through TikTok videos.
- Automatically removes videos from favorites.
- Customizable intervals for scrolling and unfavoriting.
- Pause and resume functionality with customizable durations.
- Detailed logging with optional timestamps and video counts.
- Restart functionality for easy script management.

## Usage

### Step 1: Set Up the Script
First, you need to define the CSS class selectors for the scroll button and the unfavorite button.

1. **Open TikTok in your browser.**
2. **Right-click on the scroll button** (the button you click to go to the next video) and select `Inspect` or `Inspect Element`. This will open the Developer Tools and highlight the HTML element for the button.
3. **Copy the class name** of the button. It will look something like `css-1s9jpf8-ButtonBasicButtonContainer-StyledVideoSwitch e11s2kul11`.
4. Repeat the same steps for the unfavorite button (the button you click to remove a video from your favorites). It will look something like `css-15e07yc-ButtonActionItem e1hk3hf90`.

### Step 2: Define the Selectors
Once you have the class names, update the following lines in the script with your class names:

```javascript
const rawScrollButtonSelector = 'your-scroll-button-class';  // Raw scroll button selector.
const rawUnFavoriteButtonSelector = 'your-unfavorite-button-class';  // Raw un-favorite button selector.
```

### Step 3: Copy and Paste the Script
1. Open TikTok in your browser.
2. Open the Developer Console by pressing `F12` or `Ctrl+Shift+I`.
3. Navigate to the "Console" tab.
4. Copy the script from `index.js` and paste it into the console.

### Step 4: Run the Script
Press `Enter` to run the script. The script will start running and automatically scroll through your feed, removing videos from your favorites according to the intervals and settings defined.

## Functions for manual use.

### `startScript()`
Starts the script, initiating the intervals for scrolling through videos and removing them from favorites. If a pause timer is enabled, it sets up the timer for the next pause.

### `stopScript()`
Stops the script by clearing all intervals and timers. It pauses the script, preventing further actions until it is manually restarted.

### `restartScript()`
Stops and restarts the script. Useful for reinitializing the script if it encounters issues or requires manual intervention.

## Optimization and Troubleshooting

- **Internet Speed**: Adjust the `pauseTimerInterval`, `scrollVideoIntervalMS`, and `unFavoriteIntervalMS` settings based on your internet speed. Slower internet connections may require longer intervals.
- **Avoid Simultaneous Actions**: Ensure that `scrollVideoIntervalMS` and `unFavoriteIntervalMS` are set to different values to prevent simultaneous scrolling and unfavoriting actions.
- **Handle 403 Errors**: TikTok may return a 403 error for deleted videos, causing the page to crash. If this occurs, you may need to restart the script. The script can process up to 1700 videos in one run under optimal conditions.
- **Restarting the Script**: The script includes a `restartScript()` function that can be manually called to restart the script if issues arise.

## Customization

You can customize various parameters in the script to suit your needs:
- **rawScrollButtonSelector**: The CSS class for the scroll button.
- **rawUnFavoriteButtonSelector**: The CSS class for the unfavorite button.
- **favoriteIconHref**: The href to check the favorite state.
- **pauseTimerInterval**: Interval in minutes for the pause timer.
- **pauseDuration**: Duration in minutes for the script to pause.
- **scrollVideoIntervalMS**: Interval in milliseconds for scrolling videos.
- **unFavoriteIntervalMS**: Interval in milliseconds for unfavoriting videos.
- **enablePauseTimer**: Enable or disable the pause timer.
- **enableLogs**: Enable or disable logging.
- **includeTimestamp**: Include timestamps in log messages.
- **includeVideoCountInLog**: Include video count in log messages.
- **scriptName**: Name of the script for logging purposes.

## License

This project is licensed under the MIT License.
