# farcaster-social-listening
If I make a github repo, then I have to actually start on the thing.

_Disclaimer: I am not a software engineer, my code sucks, and I am dumb._

**Note: This is totally at an "ideas" stage. Unclear if I'll actually get around to working on this. Feel free to fork / build this!**


### Use Cases (WIP)
1. **Topic Listening:** Given a topic (i.e. protocol name, EIP, company name, feature name) - answer "what is the current meta & how has it changed over time?"
   1. Understand overall sentiment, key related terms, sentiment among related terms. Who are the top influencers on each end of the sentiment & what terms do they use? Have any dates or topics led to a sentiment flip?
2. **Event Tracking:** Given some event topics (i.e. protocol release, token distribution, funding announcements) - similarly answer "what is the impact?" or "what is going right/wrong?" driven by social sentiment.
   1. Potentially also tie this to onchain activity insights. i.e. what do top users of a protocol say versus those who don't use it as frequently (may need unified identity first).

 #### Examples
- "EIP4844 sentiment is 70% positive (+10 pts month-over-month) driven byan uptick in user transaction fees commentary, led by *[X, Y, Z people]*, who all are frequent *[1, 2, 3 onchain signals]*. The 10% negative sentiment  (flat month-over-month) calls out node requirements, and state bloat, led by conversation from *[A, B, C people]* who all similarly share *[1, 2, 3 onchain signals]*. Neutral sentiment (20%) focuses on protocol specs and development timelines. The majority of this topic conversation happens in the *[op-stack]* Warpcast channel."
- "*[Insert Protocol Upgrade]* went live on mainnet 30 minutes ago. A majority (70%) of casts are celebrating lower transaction fees, but frequent user complains include "transactions getting stuck" (10%) [see top thread], "unexpected expensive transactions" (5%) [see top thread], and "wallets not updating" (2%) [see top thread].
- "*[Insert Token Distribution Announcement]* was announced yesterday. While overall sentiment is 80% negative, it is being driven by 'low social score' accounts (70% of the negative sentiment), who critiqued *[reason abc]* [see top thread], and *[reason 123]* [see top thread]. 'High social score' accounts had more mixed sentiment (60% positive, 30% negative), similarly critiquing *[reason abc]* [see top thread], but they celebrated *[reason xyz]* [see top thread].

### Steps
1. Identify topic keywords (v0: all user generated, v1: maybe gpt can give us some synonyms to help build a list)
2. Pull all casts that contain these keywords (Neynar API?) (or maybe gpt can do something smarter)
3. Store casts locally, and/or configure to store in the user's database
4. Apply social algorithms (likely try to pull some off the shelf stuff / maybe have gpt write me something / see if any open LLMs could do something better?)
5. Visualize, local streamlit and/or configure to post to a user's website?
  - Can also provide some static plotly charts

### Key References
- Neynar API: https://docs.neynar.com/reference/neynar-farcaster-api-overview
- Farcaster Protocol Dashboard (shoni_eth): https://dune.com/shoni_eth/farcaster-protocol
- Web2 Social Listening Providers (for inspo)
  - https://www.sprinklr.com/cxm/social-listening/
  - https://www.brandwatch.com/suite/consumer-intelligence/
  - https://www.quid.com/products/quid-monitor

### Other Scattered Thoughts
1. How to we integrate "wallet demographics?" Anything onchain is default public & opt-in. Also could be tricky since we only see the wallets chosen to be unveiled.
2. How do we consider frames, channels, & other Farcaster/Warpcast features that don't necessarilly exist in web2? Maybe Reddit listening is a good proxy for how to look at channels.
3. How do we filter out spammers / token farmers?
4. What other kind of "weights" can we apply (i.e. proven identity, [social score](https://dune.com/queries/3106593/5185145)
5. How do we handle for crypto-specific names that may accidently trip up sentiment algorithms (i.e. Optimism)?
