---
title: "Pocket 'Universal' Browser Extension"
publishedAt: '2025-03-02'
category: 'web'
isFeatured: true
---

For years, I've used on [Pocket](https://getpocket.com/home) to save articles I want to read later. It's an incredibly useful tool for bookmarking content across the web. However, I recently noticed that [the official Pocket extension for Google Chrome is no longer available in the Chrome Web Store](https://github.com/Pocket/extension-save-to-pocket/issues/292). This is likely due to [Google's deprecation of Manifest V2](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline?hl=en), which has affected many browser extensions.

Rather than searching for an alternative extension or tool, I found a simple workaround that lets me add articles to Pocket without installing anything extra.

# How to Save Articles to Pocket Without an Extension

You can use a bookmarklet—a small JavaScript snippet saved as a bookmark—to send the current page directly to Pocket. Here’s how:

- Right-click on the following link: <a href="javascript:(function(){var url = encodeURIComponent(window.location.href); var pocketUrl = 'https://getpocket.com/save?url=' + url; window.open(pocketUrl, '_blank');})();">Add to Pocket</a> and select Copy Link Address.
- Open your browser’s Bookmarks Manager:
  - [Google Chrome Bookmarks Manager](chrome://bookmarks/)
  - [Safari Bookmarks Manager](https://support.apple.com/guide/safari/bookmark-webpages-sfri35610/mac)
  - [Mozilla Firefox Bookmarks Manager](https://support.mozilla.org/en-US/kb/bookmarks-firefox)
- Create a new bookmark.
- Paste the copied URL into the URL field.
- Set the title as "Add to Pocket".
- Save the bookmark.

Whenever you’re on a page you want to save, simply click the bookmark, and the article will be added to Pocket automatically.

# How Does It Work?

This method leverages a simple JavaScript snippet embedded in the bookmarklet. Here’s what happens when you click it:
- The script retrieves the URL of the current tab.
- It appends that URL to getpocket.com/save.
- Pocket processes the request and saves the article to your account.

That’s it—no extensions, no complex setups, just a quick and effective way to keep your reading list organized.

```javascript
javascript:(function(){
    var url = encodeURIComponent(window.location.href);
    var pocketUrl = "https://getpocket.com/save?url=" + url;
    window.open(pocketUrl, '_blank');
})();
```

# Why This Works Well

- No need for an extension: Avoid potential security concerns and browser compatibility issues.
- Lightweight & fast: It works instantly with just a single click.
- Cross-browser compatibility: Works in Chrome, Firefox, Edge, and any other modern browser that supports JavaScript-based bookmarklets.

If you’re a Pocket user and have been missing the extension, this bookmarklet is a great alternative. Let me know if you try it out or if you have other neat workarounds for managing saved articles!
