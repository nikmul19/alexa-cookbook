# Build An Alexa HistoryBuff Skill
[![Voice User Interface](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/1-on._TTH_.png)](1-voice-user-interface.md)[![Lambda Function](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/2-off._TTH_.png)](2-lambda-function.md)[![Connect VUI to Code](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/3-off._TTH_.png)](3-connect-vui-to-code.md)[![Testing](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/4-off._TTH_.png)](4-testing.md)

## Setting up Your Alexa Skill in the Developer Portal

There are two parts to an Alexa skill.  The first part is the [Voice User Interface (VUI)](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/defining-the-voice-interface).  This is where we define how we will handle a user's voice input, and which code should be executed when specific commands are uttered.  The second part is the actual code logic for our skill, and we will handle that on [page #2](2-lambda-function.md) of this step-by-step guide.

1.  **Go to the [Amazon Developer Portal](http://developer.amazon.com).  In the top-right corner of the screen, click the "Sign In" button.** </br>(If you don't already have an account, you will be able to create a new one for free.)

<a href="http://developer.amazon.com" target="_new"><img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-1-developer-portal._TTH_.png" /></a>

2.  **Once you have signed in, click the Alexa button at the top of the screen.**

<a href="https://developer.amazon.com/edw/home.html#/" target="_new"><img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-2-alexa-button._TTH_.png" /></a>

3.  **On the Alexa page, choose the "Get Started" button for the Alexa Skills Kit.**

<a href="https://developer.amazon.com/edw/home.html#/skills/list" target="_new"><img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-3-alexa-skills-kit._TTH_.png" /></a>

4.  **Select "Add A New Skill."** This will get you to the first page of your new Alexa skill.

<a href="https://developer.amazon.com/edw/home.html#/skill/create/" target="_new"><img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-4-add-a-new-skill._TTH_.png" /></a>

5.  **Fill out the Skill Information screen.**  Make sure to review the tips we provide below the screenshot.

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-5-skill-information._TTH_.png" />

### Skill Information Tips
1.  **Skill Type** For this skill, we are creating a skill using the Custom Interaction Model.  This is the default choice.

2.  **Language** Choose the first language you want to support.  You can add additional languages in the future, but we need to start with one.  (This guide is using U.S. English to start.)

3.  **Name** This is the name that will be shown in the Alexa Skills Store, and the name your users will refer to.

4.  **Invocation Name** This is the name that your users will need to say to start your skill.  We have provided some common issues developers encounter in the list below, but you should also review the entire [Invocation Name Requirements](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/choosing-the-invocation-name-for-an-alexa-skill).

| Invocation Name Requirements | Examples of incorrect invocation names |
| ---------------------------- | -------------------------------------- |
| The skill invocation name must not infringe upon the intellectual property rights of an entity or person. | korean air; septa check |
| Invocation names should be more than one word (unless it is a brand or intellectual property), and must not be a name or place | horoscope; trivia; guide; new york |
| Two word invocation names are not allowed when one of the words is a definite article, indefinite article, or a preposition | any poet; the bookie; the fool |
| The invocation name must not contain any of the Alexa skill launch phrases and connecting words.  Launch phrase examples include "launch," "ask," "tell," "load," and "begin."  Connecting word examples include "to," "from," "by," "if," "and," "whether." | trivia game for star wars; better with bacon |
| The invocation name must not contain the wake words "Alexa," "Amazon," "Echo," or the words "skill" or "app." | hackster initial skill; word skills |
| The invocation name must be written in each language you choose to support.  For example, the German version of your skill must have an invocation name written in German, while the English (US) version must have an invocation name written in English. | kitchen stories (German skill) |

5.  **Global Fields**. For this historyBuff skill, we won't be using any audio files, video files and render templates, so you can select No for all those options. 

6.  **Click the Next button to move to the Interaction Model.**

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-6-next-button._TTH_.png" />

7.  Click on the **Launch Skill Builder** (Beta) button . This will launch the new Skill Builder Dashboard.

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-7-skill-builder-launch._TTH_.png" />

8.  Click on the **Add** button near **Intents** on the top left corner of the dashboard.

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-8-intents-button._TTH_.png" />

9.  In the textbox provided, enter the new intent name: **GetFirstEventIntent.**, and click the **Create Intent** button.

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-9-add-custom-intent._TTH_.png" />

10. Add several sample utterances for your intent.  These are the things a user would say to make this intent happen.  Here are a few examples:

* Get events for {day}
* Give me events for {day}
* What happened on {day}
* What happened

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/historybuff/getfirstevent._CB512966749_.png" />

11. Repeat the step 9 and 10 to add **GetNextEventIntent**. 

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/historybuff/intents._CB512966722_.png" />

12. Add **Slot Type** and **Slot Value**. In this skill, the slot type is **AMAZON.DATE** which is a existing slot type from Alexa's built-in library. Click **ADD+** button near **Slot Types** on the bottom left corner of the dashboard. Choosing **Use existing slot type from Alexa's built-in library**. Then searching AMAZON.DATE in the textbox and clicking **Add slot type(1)**. You don't need to provide the value manually for built-in type. 

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/historybuff/slot_type._CB512966723_.png" />
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/historybuff/Add_Slots._CB512966749_.png" />

13. After the model is build, the **Dashboard** looks like below. This skill has 5 intent types and 1 slot type.

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/historybuff/after_build-intent._CB512966722_.png" />
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/historybuff/after_build_slot._CB512966722_.png" />

14. Then click on the **Save Model** button, and then click on the **Build Model** button.

  ![](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/1-12-skill-builder-build-save-model._TTH_.png)
