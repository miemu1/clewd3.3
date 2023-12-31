<div align="center">
<a href="https://gitgud.io/ahsk/clewd/">
<h1>Clewd</h1>
  <img
    height="120"
    width="120"
    alt="Clewd"
    title="Clewd"
    src="https://gitgud.io/ahsk/clewd/-/raw/master/media/logo.png"
    align="left"
  />

</a>

<br>

[原版Clewd](https://gitgud.io/ahsk/clewd) 

[Clewd教程](https://rentry.org/teralomaniac_clewd) 
<br>
<br>
<hr>
<a href="https://gitgud.io/ahsk/clewd/-/archive/master/clewd-master.zip">
   <img src="https://gitgud.io/ahsk/clewd/-/raw/master/media/program.png">
</a>
<h2><a href="https://gitgud.io/ahsk/clewd/-/blob/master/CHANGELOG.md">CHANGELOG</a></h2>
</div>

## Requirements

nodejs>=20.4.*

## Defaults

### SettingName: (DEFAULT)/opt1/opt2...

 - `PreventImperson`: (false)/true
    * true trims the bot reply immediately if he says "Human:", "Assistant:", "H:" or "A:"
    * making it so it doesn't hallucinate speaking as you __(chance of missing some spicy things)__

 - `PromptExperiments`: (true)/false
    * true is an alternative way to send your prompt to the AI
    * experiment before setting to false

 - `RetryRegenerate`: (false)/true
    * true uses the AI's own retry mechanism when you regenerate on your frontend
    * instead of a new conversation
    * experiment with it

 - `SystemExperiments`: (true)/false
    * only has any effect when `RenewAlways` is false
    * true alternates between Main+JB+User and JB+User
    * false doesn't alternate

 - `RenewAlways`: (true)/false
    * true makes a new conversation context each time
    * false *tries* to reutilize the same old conversation, sending only your actual last message each time, taking into consideration `SystemExperiments`

 - `StripAssistant`: (false)/true
    * true strips the "Assistant:" prefix from the last assistant message

 - `StripHuman`: (false)/true
    * true strips the "Human:" prefix from the last human message

 - `AllSamples`: (false)/true
    * mutually exclusive with `NoSamples`
    * true converts all real dialogue to "sample dialogue"
    * you're "H" and the AI is "A"
    * whatever the AI replies with is kept (only outgoing)
    * [see this](https://docs.anthropic.com/claude/docs/prompt-troubleshooting-checklist#the-prompt-is-formatted-correctly) for more information
    - Human->H
    - Assistant->A

 - `NoSamples`: (false)/true
    * mutually exclusive with `AllSamples`
    * true converts all "sample dialogue" to real dialogue
    * you're "Human" and the AI is "Assistant"
    * whatever the AI replies with is kept (only outgoing)
    * [see this](https://docs.anthropic.com/claude/docs/prompt-troubleshooting-checklist#the-prompt-is-formatted-correctly) for more information
    - H->Human
    - A->Assistant
	
 - `LogMessages`: (false)/true
    * true logs prompt and reply to `log.txt`

 - `ClearFlags`: (false)/true
    * possibly snake-oil
    * clears your warnings

 - `PassParams`: (false)/true
    * true will send the temperature you set on your frontend
    * only values under <=1.0 >= 0.1
    * this could get your account banned
    * if clewd stops working, set to false

 - `PreserveChats`: (false)/true
    * true prevents the deletion of old chats at any point



## Examples

**safe setup**
> **PreventImperson**: false (higher chance of spicy stuff)

> **RenewAlways**: true

---

**experimental setup**
> **PromptExperiments**: true

> **SystemExperiments**: true

> **RetryRegenerate**: true

> **StripAssistant**: true (add prefill to jailbreak in this case)

> **PreventImperson**: true

> **RenewAlways**: false
