# 🔎 Analysis of Oreans
### Looking inside CodeVirtualizer, Themida, and WinLicense

<!--  -->

## Notice

Copyright (c) 2020, https://github.com/quosego
All rights reserved.

This repository is protected by copyright, but is able to be obtained from any reproduction, storage in a retrieval system, or transmission in any form or by any means, electronic, mechanical, photocopying, recording, or likewise as the contents of this repository are openly accessible online. 

<!--  -->

## Preface

Protecting binaries through obfuscation and has become the goto standard in defensive and offensive software alike. [Oreans](https://www.oreans.com/) is a notorious ‘pioneer’ in utilizing a GUI based software protection application that is easy to access and has little complexity to the end user. 

However, even after several years, reverse engineers studying Oreans protected binaries still struggle to analyze all the modifications done by Oreans and mistake and mislabel certain features Oreans provides. Several research papers mystify the process of analyzing Oreans Technologies. This repository can help provide transparency to certain biases regarding the  speeds and complexities of Oreans which in turn helps provide more accuracy to researchers.

The documentations and reference code within this repository are primarily focused on targeting x86 binaries. However, future information supporting x64 binaries may be provided at a later date.

<!--  -->

### Acknowledgments

First of all, I would like to thank you, the reverse engineering community, for making this possible. The incredible effort of all the work put in over the years, the collective effort in pushing the underground reversing scene into the public, the openly helpful support, and the limitless curiosity of the scene has been a basis for the evolution of myself and the work I've been able to produce over the years.

I would especially like to thank everyone who reviewed the drafts for this repository and provided valuable feedback, help, support, and adjustiments. These reviews increased the quality of the repository significantly, again proving that the collective "wisdom" of many talented individuals is better than that of a single individual. Therefore, so far (this list is growing and will be updated) a huge thanks to [DBLmao](https://www.youtube.com/channel/UC-DRTkNc9l2FM8Da0zfML9w), [Shavit](https://github.com/shavitush), [JP](https://github.com/jnpl95), [Erik](https://github.com/MinimumDelta), and [Rajan](https://github.com/RajanGrewal).

In addition, I would like to thank everyone from OpenRCE.org, ExeTools.com, Tuts4You.org, Reverse4You.org, Rohitab.com, PEDIY.com, GuidedHacking.com, UnknownCheats.me, RaGEZONE.com, Rebirth.dev, and the several other communities (board.b-at-s.info, ccplz.net, kernelmode.info, ic0de.org, rbmc.tw, unallied.com, gamersoul.com, reversing.ro, moopler.net, snsgaming.com, mapleninja.us, opensc.ws, progamercity.net, mmolazy.com, and wecodez.com) that have came and gone over the years. In addition to all the work involved in reverse engineering and hacking games, several of these people in these communities spent many, many hours explaining and discussing their work with me, and the did so with patience and enthusiasm; I will always be indebted.

A special thanks goes to those who were able to meet me in this world but passed on too soon. I'll always cherish the memories. 

And finally, many thanks goes to you, the readers.

## Contents

* Repositories
    * Documentations
        * Version 2
            * [CodeVirtualizer](https://github.com/quosego/analysis.oreans.codevirtualizer/tree/v2)
            * [Themida](https://github.com/quosego/analysis.oreans.themida/tree/v2)
            * [WinLicense](https://github.com/quosego/analysis.oreans.winlicense/tree/v2)
        * Version 3
            * [CodeVirtualizer](https://github.com/quosego/analysis.oreans.codevirtualizer/tree/v3)
            * [Themida](https://github.com/quosego/analysis.oreans.themida/tree/v3)
            * [WinLicense](https://github.com/quosego/analysis.oreans.winlicense/tree/v3)
    * References
        * [Plugins](https://github.com/quosego/analysis.oreans/tree/plugins)
        * [Scripts](https://github.com/quosego/analysis.oreans/tree/scripts)
        * [Tools](https://github.com/quosego/analysis.oreans/tree/tools)

<!--  -->

## About

After getting some great feedback from my original repository under the alias [quosego](https://github.com/quosego/analysis.oreans), which can still be seen via [gavz's fork](https://github.com/gavz/analysis.oreans), I've decided to improve my work and step it up a bit. 

Within this repository there exists links to documentations and reference code to help guide those who are studying Oreans Technologies and provide solutions for understanding how certain features work, how to identify certain features, and if needed, how to bypass certain features. 

The focus from this repository lies on the features that Oreans provides and demonstrates how features can impact day-to-day analysis and how can you can benefit from them in additional projects and/or binary optimization. 

<!--  -->

### What to Know

To get the most from this repository, you should already be familiar with Windows Process Executables, Windows API, x86 Assembly Language, C++ or Python. It is recommended that you have experience using a disassembler and a debugger and have used some type of low level language optimization technology.

However, you do not have to be an expert. My goal is to make the content understandable for the average researcher be it hobby or career.

Nevertheless, I will discuss basic features and review more subtle issues as the need arises. This ensures that the text is accessible to experts and intermediate researchers alike.

<!--  -->

### How to Read

Do not be afraid by the overwhelming complexity in this repository. As always with low level assembler languages, things can become pretty complicated when you look into the details. For a basic understanding, certain documentations may be easier to understand than others. I advise skimming over each documentation first to see if you are able to understand the parts first.

In my experience, the base way to learn something new is to look at the examples. While the actual binaries for the documentations are not provided, I attempt to provide examples when possible and cross link with any reference that would be avaliable for the current topic. With this information you should be able to reproduce certain situations and if needed, follow along with the documentation processes.

<!--  -->

## Feedback

I welcome your constructive input - both negative and positive. I will continue to try to provide updates when able. At some point you may find errors, inconsistencies, or methods that could be improved, or are missing altogether. Your feedback is critical to help improve future revisions.

The best way to reach out is by opening a new issue in this repository:

https://github.com/quosego/analysis.oreans/issues

Please be sure to refer to what your situation is when giving feedback and if possible link or provide an example of the topic in question.

Many thanks.

<!--  -->

<hr />

<!--  -->

<p align="center">
  <a href="https://hits.seeyoufarm.com/api/count/graph/dailyhits.svg?url=https://github.com/quosego/analysis.oreans">
    <img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fquosego%2Fanalysis.oreans&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=true" alt="repository hits">
  </a>
  <a href="https://github.com/quosego/analysis.oreans/watchers">
    <img src="https://img.shields.io/github/watchers/quosego/analysis.oreans?style=flat-square" alt="watchers"/>
  </a>
  <a href="https://github.com/quosego/analysis.oreans/stargazers">
    <img src="https://img.shields.io/github/stars/quosego/analysis.oreans?style=flat-square" alt="stars"/>
  </a>
  <a href="https://github.com/quosego/analysis.oreans/network/members">
    <img src="https://img.shields.io/github/forks/quosego/analysis.oreans?style=flat-square" alt="forks"/>
  </a>
</p>

<!--  -->

<p align="center">
  <a href="https://github.com/quosego">
    <img width="64" heigth="64" src="https://avatars3.githubusercontent.com/u/73345443" alt="quosego"/>
  </a>  
</p>
