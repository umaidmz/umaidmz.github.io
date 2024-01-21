---
title: Day 1 of Job Hunting for Data Science roles
tags: [Job Hunting, Data Science, Machine Learning]
style: fill
color: info
description: Today I formally started putting my heart and mind together to control my life and set milestones for myself.
---

A few weeks ago, I graduated from the University of Waterloo with an MS Degree in Data Science and Artificial Intelligence. Before graduation, I was confident in my qualifications and abilities, anticipating a swift transition into a full-time Data Scientist role. However, the reality of the job market proved to be a humbling experience.

Post-graduation, I embarked on my job search, tapping into alumni networks and industry contacts for insights. Despite feeling a strong alignment with the roles I applied to, responses were not forthcoming. A recent enlightening discussion over coffee with industry professionals shifted my perspective. It revealed that my approach of meticulously tailoring each resume for specific job roles, while thorough, was not the most efficient strategy, limiting me to applying for only a handful of positions daily.

This realization led me to adopt a four-pronged approach: maintaining motivation, fine-tuning my resume to better match each position, diligently preparing for interviews, and dedicating time to personal learning projects that fuel my passion. This post serves as a reminder and a "time capsule" of sorts, capturing a challenging phase in my professional journey. I'm optimistic about the future and remain confident that the right opportunity is on the horizon.

As I navigate this journey, I am focused on continuous growth and learning. Embracing every setback as a learning opportunity, I am refining my approach, enhancing my skills, and expanding my understanding of the industry. This period is not just about finding a job; it's about personal and professional development, and finding a role where I can truly make an impact.

I write this as a message to my future self and to others who may be facing similar challenges: persistence, adaptability, and a willingness to learn are key. The journey may be tough, but it's preparing me for a fulfilling career ahead. To those considering me for roles, know that I bring not only technical expertise but also resilience, a growth mindset, and a readiness to contribute meaningfully to your team.

Looking back at this one day, I hope to remember these moments as pivotal in shaping a successful career in data science. I am eager and ready for the opportunities that lie ahead.

## Job Applications

Today, I bypassed the usual morning routine and dove straight into job applications. By 7:30 AM, I was up, breakfasted, and ready to tackle the challenge head-on. My focus was razor-sharp as I navigated through various job portals, submitting my resume to around 30 positions. My targets were diverse yet specific to my expertise – roles in machine learning, data science, data engineering, and data analysis.

By 1 PM, after a morning of intense focus and dedication, I took a well-deserved break. It was time to step away from the applications, recharge, and catch up with family. This brief interlude was as much about maintaining balance as it was about reflecting on the productive morning.

## Interview Preparation

Having been through Coop, then adjusting in a new place, getting married and in the midst of job hunting, I became very rusty with my ML. I decided to go through a book which I always carry around in my laptop: Hands-on ML with Scikit Learn, Keras and TF. Now that I went through Chapter 2: End-to-end ML predictive model, I realize that feature engineering is more important in the industry than just deep learning (I was a neural net only kind of guy who though these ML models will go no where). The industry is still yet to adopt these GPU intensive models in production. These are things that I learnt today:

- Stratified Train Test Splt: Split the train and test set while making sure that the ration of samples based on a specific category is the same to prevent bias.

```
from sklearn.model_selection import StratifiedShuffleSplit
split = StratifiedShuffleSplit(n_splits=1, test_size=0.2, random_state=42) for train_index, test_index in split.split(housing, housing["income_cat"]):
        strat_train_set = housing.loc[train_index]
        strat_test_set = housing.loc[test_index]
```