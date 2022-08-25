---
layout: post
title: "Hosting Red Alert 2 Server on Cncnet"
---
Red Alert 2 is a twenty years old epic PC game built by [Westwood Studios](https://en.wikipedia.org/wiki/Westwood_Studios). I remember that we were using [Hamachi](https://en.wikipedia.org/wiki/LogMeIn_Hamachi) for playing online RA2. You could only play with your friends who joined your Hamachi network. As you can see, It was ugly and hacky solution.

In 2009, [CnCNet](https://cncnet.org/what-is-cncnet) community (not associated with EA games) was established. CnCNet provides an online platform for Command and Conquer games (like Red Alert 2, Yuri’s Revenge, Tiberian Sun). Therefore, You can play these games online like CS:GO.

I’ve discovered CnCNet in Covid-19 isolation. We’ve been playing RA2 online almost every night with my friend 
Umut [like the good old days](/public/images/posts/cncnetserver/playing-pc-with-umut.jpg).

Bad news, There aren’t any CnCNet servers in Turkey. However, CnCNet let you host your own server. I’ve dockerized their tool and [published on Docker hub](https://hub.docker.com/r/efeoge/cncnet_server). Therefore, It will be 
easier to run.

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
