---
layout: post
title: "[Python] Study of Discord Bot"
excerpt: "디스코드봇 공부"
category: Python
tags: [python, discord]
comments: false
---
<figure class="half">
    <a href="https://discord.com/"><img width="600px" src="{{ site.url }}/assets/img/discord.png"></a>
    <figcaption>Discord 로고의 모습.(디스코드 홈페이지로 이동)</figcaption>
</figure>

## Discord?
Discord는 음성, 채팅, 화상통화 등을 지원하는 인스턴트 메신저이다. 한국에서는 주로 온라인 게임을 즐기는 사람들이 많이 이용하는 편이며, <br>
뛰어난 성능과 간편함을 바탕으로 그 이전에 게임 유저들이 애용하던 여러 보이스 메신저들을 제치고 주류로 올라서는데 성공했다. 사실상 게임용 메신저의 대명사.<br>

## discord.py
discord.py를 이용해 파이썬으로 디스코드 봇을 만들 수 있다. <br>
오늘은 discord.py를 이용해서 파이썬에서 디스코드 봇을 만들어보려고 한다.<br>

discord.py를 이용하려면, discord 모듈을 다운받아야 한다.<br>
cmd 창에서 `pip install discord` 를 쳐서 discord 모듈을 다운받았다.<br>

## import
본격적으로 discord 모듈을 사용하려면 discord 모듈을 `import` 해줘야한다.
```py
import discord
from discord.ext import commands
```
