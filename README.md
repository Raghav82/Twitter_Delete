
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>X (Twitter) Mass Delete – README</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 20px;
            max-width: 900px;
        }
        h1, h2 {
            color: #333;
        }
        h1 {
            border-bottom: 2px solid #333;
            padding-bottom: 10px;
        }
        code {
            background-color: #f4f4f4;
            padding: 2px 6px;
            border-radius: 4px;
            font-family: monospace;
        }
        pre {
            background-color: #f4f4f4;
            padding: 10px;
            border-radius: 6px;
            overflow-x: auto;
        }
        ul, ol {
            margin-left: 20px;
        }
        a {
            color: #007acc;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
        .important {
            color: #b30000;
            font-weight: bold;
        }
    </style>
</head>
<body>

<h1>X (Twitter) Mass Delete – UI Automation (No Tokens Required)</h1>

<h2>Overview</h2>
<p>This script automates the deletion of tweets and undoing reposts directly through the X (Twitter) web interface. It mimics the manual steps you would take in the browser, requiring <strong>no API keys, tokens, or external tools</strong>. It works with your existing logged-in session.</p>

<h2>Why This Approach?</h2>
<p>I created this script because I was <strong>unable to download my Twitter archive</strong> due to a bug, which prevented me from using the other popular archive-based deletion method. This solution uses the same UI flows you would click manually, making it simple and accessible.</p>

<h2>Features</h2>
<ul>
    <li>Iterates through visible tweet cards on your <strong>Posts</strong> or <strong>Replies</strong> tab.</li>
    <li>Opens the overflow menu for each tweet.</li>
    <li>Clicks <strong>Delete</strong> and confirms, or attempts <strong>Undo repost</strong> if applicable.</li>
    <li>Scrolls to load more tweets and repeats until no more actionable items remain.</li>
</ul>

<h2 class="important">Important Notes</h2>
<ul>
    <li><span class="important">Irreversible:</span> Deletions cannot be undone. If possible, export your archive first.</li>
    <li><span class="important">Rate Limits:</span> Backend limits still apply (~50 deletes per 15 minutes; ~300 per 3 hours). <a href="https://docs.x.com/x-api/posts/manage-tweetstionOfficial Docs</a></li>
    <li><span class="important">Fragile Selectors:</span> X’s UI/DOM may change over time. You might need to tweak selectors. <a href="https://stackoverflow.com/questions/64863099/deeets-with-js-consoleCommunity Discussion</a></li>
</ul>

<h2>How to Use</h2>
<ol>
    <li>Open your X (Twitter) profile in a browser (Posts or Replies tab).</li>
    <li>Open the <strong>Developer Console</strong> (F12 → Console).</li>
    <li>Paste the script and press <strong>Enter</strong>.</li>
    <li>Keep the tab focused while the script runs.</li>
</ol>

<h2>Configuration</h2>
<p>You can adjust these constants to control pacing and reduce rate-limit errors:</p>
<pre><code>
const CLICK_DELAY_MS = 1200;   // Delay after clicks
const SCROLL_DELAY_MS = 1800;  // Wait after scrolling
const MAX_RETRIES = 3;         // Retries for menu actions
const SHORT_PAUSE_MS = 500;    // Small spacing between tweets
</code></pre>

<h2>References</h2>
<ul>
    <li>https://docs.x.com/x-api/posts/manage-tweets/introductionManage Posts – Official Docs</a></li>
    <li><a href="https://stackoverflowtions/64863099/deleting-tweets-with-js-consoleStackOverflow Discussion on UI Selectors</a></li>
    <li><a href="https://chrissblog/2024/bulk-deleting-tweets/Community Scripts &amp; Blog Posts</a></li>
    <li><a href="https://gist.github.com/lucahammer/1aa16b4d3c1fb04035839da5ef699d65ple</a></li>
</ul>

<h2>Disclaimer</h2>
<p>Use at your own risk. This script interacts with the live UI and may break if X updates its DOM structure.</p>

</body>
</html>
