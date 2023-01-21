# Audible Bookmarks
Tools for easily extracting bookmarks and notes in note-friendly formatting.

### Audible Book to Player
From the Audible book page to the web player for that book. This is equivalent to clicking "Play" on the page, with added convenience of it not opening in a new reduced window, allowing bookmarklets to still be available in the main browser window.

<a href='javascript:location.href=location.href.replace(/\?.+/,"").replace(/.co.uk\/.+\//,".co.uk/webplayer?asin=");'>Audible Book to Player</a> <- Drag this to bookmarks bar to use.


### Audible Bookmarks
From the audible cloud player in browser for the audiobook needed, pause the player (if you want), wait for it to load then click `...` on the page, followed by `Bookmarks` from the list that appears. When your bookmarks then load, click on this bookmarklet, and the notes will be copied to clipboard in a concise markdown format.

NOTE! The default audible view for bookmark clips/note is from most recently created at the top to oldest at the bottom. Since bookmarks are typically created in order of listening, this also reverses the order of the notes from the page to a more sensible order.

<a href="javascript:(function()%7BallBookmarks%3D%5B...document.querySelectorAll(%22.adblCpBookmarkArea%3Anot(%23adbl-cp-bookmark-list-row-%5C%5C%7B0%5C%5C%7D%22)%5D.reverse()%2CallBookmarksFormatted%3D%22%22%2CallBookmarks.forEach((o%3D%3E%7BchapterAndTimeStamp%3Do.querySelector(%22.adblCpBookmarkPosition%22).innerText%2CbookmarkNoteText%3Do.querySelector(%22.adblCpBookmarkNote%22).innerText%2CbookmarkLinkAddress%3Do.querySelector(%22.adblCpBookmarkStart%22).href%2CformattedFullBookmarkNote%3D'%22'%2BbookmarkNoteText.trim()%2B'%22%5Cr%5Cn*'%2BchapterAndTimeStamp.trim()%2B%22%20-%20%5BBookmark%20Link%5D(%22%2BbookmarkLinkAddress%2B%22)*%22%2CbookmarkNoteText.trim().length%3E0%26%26(allBookmarksFormatted%3DallBookmarksFormatted%2B%22%5Cr%5Cn%5Cr%5Cn%22%2BformattedFullBookmarkNote)%7D))%2CallBookmarks%5B0%5D.focus()%2Cnavigator.clipboard.writeText(allBookmarksFormatted)%7D)()">Audible Bookmarks </a> <- Drag this to bookmarks bar to use.

**GitHub may break the link - you can copy paste the below as a link for the bookmarklet**
```javascript
javascript:(function(){allBookmarks=[...document.querySelectorAll(".adblCpBookmarkArea:not(#adbl-cp-bookmark-list-row-\\{0\\}")].reverse(),allBookmarksFormatted="",allBookmarks.forEach((o=>{chapterAndTimeStamp=o.querySelector(".adblCpBookmarkPosition").innerText,bookmarkNoteText=o.querySelector(".adblCpBookmarkNote").innerText,bookmarkLinkAddress=o.querySelector(".adblCpBookmarkStart").href,formattedFullBookmarkNote="\""+bookmarkNoteText.trim()+"\"\r\n*"+chapterAndTimeStamp.trim()+" - [Bookmark Link]("+bookmarkLinkAddress+")*",bookmarkNoteText.trim().length>0&&(allBookmarksFormatted=allBookmarksFormatted+"\r\n\r\n"+formattedFullBookmarkNote)})),allBookmarks[0].focus(),navigator.clipboard.writeText(allBookmarksFormatted);})()
```
