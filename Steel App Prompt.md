type: idea
categories:
  - "[[Ideas]]"
  - "[[Dumps]]"
project:
  - "[[Steel]]"
tags:
  - "#steel-card"
  - "#steel-app"
acted-on: true
compiled: 2026-08-10
backlog: "- AI section behavior detailed below (expanded in steel-by-exo-ecosystem.md Appendix 2026-08-10) - CoreNFC context files to attach - task: state/tasks/steel-app-nfc-spec.md (append AI-mode section)"
---

Alright, I’m going to ramble off some thoughts I had and you help me structure then so Claude opus can implement them.

---
First and foremost the app must have NFC functionality. — not just UI. So there will be needed files or settings we will add soon. Let’s start the foundation of that. Later I will attach some files for context from — https://developer.apple.com/documentation/corenfc
—-
For now we polish UI finishes for UI prototype.
in the Recent Connections page, it should have a slide feature (within the dive/container/button — per recent connection.) that brings the profile picture to the far right when it’s slid, with all the descriptions disappearing.. and then three new buttons should appear post slide one for three dot drop-down for extra settings per that connection. Another button next to that one should be for hide recent connection. And another with the two chat bubble icon overlapping under that one will be called AI. to recap the first option when it slid is the three dotted button that drops down more options, (e.g. trash, settings, etc..) — the next button after that should be a hide button. And after that one should be a double chatted icon that is called AI. The other two are self-explanatory, but the AI button will lead to the AI section which I will explain soon.

there also should be a new icon among the other icons (in between venues and events), named “trust” with a gold coin icon.

What the card is disabled there should be a shield red icon replacing the green active button. Also when the card is enabled I cannot see the Gold shadow on mobile, make sure this is visible as it seems fine on desktop, but not visible on mobile in active state.

Moving on, we will now discuss the main AI section I mentioned earlier. this is how I would like it to be. in the default home screen where the main card component is, we will a new ui functionality, while keeping the one we have as default. This is how we will enter AI mode: when the steel card is pulled down (similar to like when a refresh action is taken), the card will expand and drag down showing a full screen, vertical card display. [this will also be the UI steel card that potential customers who do not have the app view on the web version during a shareable interaction] *this section is important viral coefficient* — 
minimalist aesthetic with a profile div for user in the upmost top to the right for the user picture. next wish will be a notification bell icon that is small. at the very bottom of the screen, there should be a chat bar when the bar is pressed the vertical full screen card should rise naturally to fit; but in a collapsing fashion. -collapsing upward into a slim announcement bar with the profile picture to the right of the announcement bar within it still showing ever so slightly. To the left of the announcement bar should be branded “steel card”. And the way the functionality works is when the announcement bar is pull down. The vertical steel car returns from the collapsed date to the regular full screen state, dropping the keyboard and bringing the chat bar back to the bottom of the screen. There was no need to add the name of the user in the AI screen Space. Moving forward, there should be a placeholder for our logo in the middle of the chat screen (similar to the attached image), and in the middle of the screen underneath the placeholder logo, there should be a greeting similar to that attached image (e.g., how can I help you this evening?) 
— also to the far left of the announcement bar div should be the small three lines button that would open up a left side bar to show recent chat history. Make sure this is collapsible.   

When the steel card vertical edition is present, and the user wants to return to the home section, they must press the home button that already exist. this will reset the functionality. in fact, this should be the main real steel connect dashboard. Nevertheless, we will keep the current user interface we have for home except that will be the secondary, for instance, once a user opens the app. They will see this new section I’ve created. If they hit home once more, they will then enter the current UI that is in place showing the expanded version (what we have already in place now). The default home will become the version I just described.

take your time to understand this in my minute detail, so that we can comprehensively make this a great prompt. Before making it a great prompt for established that you understand each section and let’s go over it. 

ATTACHED: 
* read me file for NFC core that we will later use for foundation.
* chat bar slim styling with plus/diction symbol and emerald green send button
* placeholder logo and greeting example