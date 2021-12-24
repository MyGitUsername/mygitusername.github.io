---
layout: post
title:  "Add a Youtube Channel to RSS"
date:   2021-12-23
---

1. Get the channel's id 
    - Navigate to the desired youtube channel 
    - View the page source
    - Search for `channelId` 
2. Specify the feed url using the format `https://www.youtube.com/feeds/videos.xml?channel_id=THE_CHANNEL_ID_HERE` 
in your respective RSS reader


Unforunately, youtube's RSS feed does not contain an embedded video; instead, it provides a link
to watch the video on their website.  If you prefer to avoid 
youtube.com altogether options include:

1. Download the video using the link provided with [youtube-dl] [youtube-dl]
2. Use [mpv] [mpv] to stream the video
3. Use the open source youtube frontend [Invidious] [Invidious] with a redirector
(e.g., [Redirector] [redirector] or [Privacy Redirect] [privacy redirect])

Sources:  
[Hacker News: Youtube and RSS] [hn youtube and rss]  
[Hacker News: Privacy Respecting Frontends] [hn privacy respecting frontends]  

[Invidious]: https://invidious.io/
[Vimium]: https://vimium.github.io/
[youtube-dl]: https://github.com/ytdl-org/youtube-dl
[hn youtube and rss]: https://news.ycombinator.com/item?id=26014344&p=2
[hn privacy respecting frontends]: https://news.ycombinator.com/item?id=29662235
[mpv]: https://mpv.io/
[redirector]: https://github.com/einaregilsson/Redirector
[privacy redirect]: https://github.com/SimonBrazell/privacy-redirect
