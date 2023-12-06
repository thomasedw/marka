# marka showcase 🎓<~>👀🤖

> What's marka?

Marka was a side project™ that I worked on in my spare time to explore how well newer LLM's could be applied to in an education context, specifically for automated marking.

This repository is a showcase of what was achieved, my thoughts on next steps and examples of some initial adversarial tests.

![An AI marked exam question on chemistry, asking: "Barium chloride can be prepared from barium hydroxide in a neutralization reaction. Write the equation for this reaction. State symbols are not required". The answer given is: "Ba(OH)2 + 2HCl -> BaCl2 + 2H2O"](./chemistry-equation-example.png)

## 🧠 LLM's are smart, let's see how well they do on exams!

...was a popular headline a while ago before ChatGPT became a household name. After seeing the _buzz_ around how well they could perform on exams themselves, I wondered how easy it would be to get them to grade papers as-well. 

Grading a paper is a difficult task - it requires deeper understanding of the topic at hand, and is often ambiguous - two graders may give different scores depending on their own opinion. The ambiguity is actually a benefit for the application of a deep neural network here in my opinion (granted that you introduce a unknown bias into this) as the complex models available today can solve tasks that otherwise traditional algorithmic approaches could not.

For example, a traditional approach to exam grading is a simple equality comparison. But for anyone who has ever used any form of online grading tools in the past would recognize, this is often fraught with potential problems.

```math
100m^2 \ne 100\hspace{1mm}m^2
```

Without heavily restricting user input, or thinking of alternative UX approaches to input, the above example of spacing is one example of many that can lead to frustration.

## 🏁 Matching problems

AI has solved many matching problems. Starting from the classic problem of determining handwritten text, [MNIST](https://paperswithcode.com/dataset/mnist) is one dataset which highlights this problem, there are several ways to draw the same concept and a common approach to match these two ambiguous definitions is to use a neural network as a classifier.

Marking exam answers can also be interpreted as the same problem, as long as the mark scheme has sufficient detail around the concept you are marking.

Following this thinking and a few trial and error experiments later, here are some examples of what was created:

|![An AI marked exam question on chemistry, asking: "Barium chloride can be prepared from barium hydroxide in a neutralization reaction. Write the equation for this reaction. State symbols are not required". The answer given is: "BaOH2 + 4HCl + 2FeHO -> BaCl2 + 10H2O"](chemistry-equation-incorrect-example.png)|
|:-:|
|An example of an incorrect answer ❌|

### 🧪 Testing, testing, testing...

After achieving somewhat of a breakthrough, adversarial attempts were tested and were awarded full marks at first 😢

After some additional trial and error, a better result was found for adversarial/prompt injection techniques...

|![An example showing a user attempting to gain marks adversarially by attempting prompt injection techniques and showing the AI awarding 0 marks.](adversarial-attempts.png)|
|:-:|
|An example showing an adversarial attempt to gain marks 🕵️|

|![An example showing an AI marked answer to a geography paper question on outlining a strategy used to manage energy consumption.](descriptive-marking.png)|
|:-:|
|An example showing a question from a Geography paper, which allows students to state points in many different ways and forms.|

## 💭 Closing thoughts

This project was an interesting look into LLMs, prompting, adversarial prompt injection techniques and I explored a few new tools and frameworks along the way (like [tRPC](https://trpc.io/) and [prisma](https://www.prisma.io/)). I think there's potentially a lot of time that can be saved through the approaches list here, however care needs to be taken that such systems are resilient and accurate - especially when used to educate others. 

More work is needed in trialing further approaches to the marking process and I would look into allowing the model to query reputable sources for additional information on concepts if they are not described comprehensively in the exam mark schemes.