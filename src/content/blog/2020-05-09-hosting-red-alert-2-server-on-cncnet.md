---
title: "Hosting Red Alert 2 Server on Cncnet"
publishedAt: '2020-05-09'
---
Red Alert 2 is an epic PC game that was released twenty years ago by [Westwood Studios](https://en.wikipedia.org/wiki/Westwood_Studios). I remember using [Hamachi](https://en.wikipedia.org/wiki/LogMeIn_Hamachi) to play RA2 online; it allowed you to play only with friends who joined your Hamachi network. As you can imagine, it was quite an inelegant and makeshift solution.

In 2009, the [CnCNet](https://cncnet.org/what-is-cncnet) community (unaffiliated with EA Games) was established. CnCNet provides an online platform for Command and Conquer games, including Red Alert 2, Yuri’s Revenge, and Tiberian Sun. This means you can now enjoy playing these games online, much like CS:GO.

I discovered CnCNet during the Covid-19 isolation period. My friend Umut and I have been playing RA2 online almost every night, just [like the good old days](/public/images/posts/cncnetserver/playing-pc-with-umut.jpg).

The downside is that there are no CnCNet servers in Turkey. However, CnCNet allows you to host your own server. I've dockerized their tool and [published it on Docker hub](https://hub.docker.com/r/efeoge/cncnet_server), making it easier for everyone to run.

<center><img src="/public/images/posts/cncnetserver/done.gif" title="new construction options"></center>

## Instructions
- [Install Docker](https://docs.docker.com/get-docker/) on your server.
- Run `docker run --restart=unless-stopped -d -p 50001:50001 efeoge/cncnet_server --port 50001 --name “Cool 
name of your server” --maxclients 200` on your server.
- Wait for 24 hours to appear in the server lists.
- Play. 🎉

Finally, I've distinguished that I'm still a noob in a game which I played 15 years ago. What a shame! [Bryan 
Vahey](https://www.youtube.com/user/pwn2kill22) has amazing Red Alert 2 gameplays. Take a look them if you'd 
like to enhange your gameplay.
