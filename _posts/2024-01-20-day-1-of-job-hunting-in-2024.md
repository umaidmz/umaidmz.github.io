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

My recent experiences, including a Coop program, relocating, getting married, and job hunting, led to a temporary detachment from my machine learning skills. To regain my proficiency, I revisited a trusted resource that's always with me on my laptop: 'Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow'.

Diving into Chapter 2, which focuses on building an end-to-end machine learning predictive model, was particularly enlightening. It shifted my perspective on the role of feature engineering in the industry. Previously, I was heavily inclined towards deep learning and neural networks, somewhat skeptical about the practical utility of traditional ML models. However, this chapter opened my eyes to the reality that feature engineering often holds more significance in real-world applications than solely relying on deep learning.

One key realization is that the industry hasn't fully embraced GPU-intensive models in production yet. This has broadened my understanding of the diverse approaches in machine learning and the importance of balancing innovative techniques with practical, industry-standard methods.

- Stratified Train Test Splt

```
from sklearn.model_selection import StratifiedShuffleSplit
split = StratifiedShuffleSplit(n_splits=1, test_size=0.2, random_state=42) for train_index, test_index in split.split(housing, housing["income_cat"]):
        strat_train_set = housing.loc[train_index]
        strat_test_set = housing.loc[test_index]
```

- Finding Correlations and Joining Attributes

```
from pandas.plotting import scatter_matrix
    attributes = ["median_house_value", "median_income", "total_rooms",
                  "housing_median_age"]
    scatter_matrix(housing[attributes], figsize=(12, 8))
```

- Handle text and categorical data with One-Hot Encoder
- Use custom Transformers in Scikit Learn

```
from sklearn.base import BaseEstimator, TransformerMixin
    rooms_ix, bedrooms_ix, population_ix, households_ix = 3, 4, 5, 6
class CombinedAttributesAdder(BaseEstimator, TransformerMixin):
def __init__(self, add_bedrooms_per_room = True): # no *args or **kargs
self.add_bedrooms_per_room = add_bedrooms_per_room def fit(self, X, y=None):
return self # nothing else to do def transform(self, X, y=None):
rooms_per_household = X[:, rooms_ix] / X[:, households_ix] population_per_household = X[:, population_ix] / X[:, households_ix] if self.add_bedrooms_per_room:
bedrooms_per_room = X[:, bedrooms_ix] / X[:, rooms_ix]
return np.c_[X, rooms_per_household, population_per_household,
bedrooms_per_room]
return np.c_[X, rooms_per_household, population_per_household]
else:
attr_adder = CombinedAttributesAdder(add_bedrooms_per_room=False)
    housing_extra_attribs = attr_adder.transform(housing.values)
```

- Use tranformation pipelines and feature scaling for numerical data
```
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
    num_pipeline = Pipeline([
            ('imputer', SimpleImputer(strategy="median")),
            ('attribs_adder', CombinedAttributesAdder()),
            ('std_scaler', StandardScaler()),
        ])
    housing_num_tr = num_pipeline.fit_transform(housing_num)
```

- Try multiple models and use cross validation to make sure theya re not overfitting

```from sklearn.model_selection import cross_val_score
scores = cross_val_score(tree_reg, housing_prepared, housing_labels,
                             scoring="neg_mean_squared_error", cv=10)
    tree_rmse_scores = np.sqrt(-scores)
```

- Use Grid Search or Randimzed Search to finetune models

```
from sklearn.model_selection import GridSearchCV
    param_grid = [
        {'n_estimators': [3, 10, 30], 'max_features': [2, 4, 6, 8]},
        {'bootstrap': [False], 'n_estimators': [3, 10], 'max_features': [2, 3, 4]},
]
    forest_reg = RandomForestRegressor()
    grid_search = GridSearchCV(forest_reg, param_grid, cv=5,
                               scoring='neg_mean_squared_error',
                               return_train_score=True)
    grid_search.fit(housing_prepared, housing_labels)
```

## Self-Learning

Recently, I've taken a bit of a deep dive into the world of Hugging Face, a territory that's both familiar and uncharted for me. My past encounters with this library were pretty straightforward – it was all about getting models up and running for my projects, more of a 'get things done' approach. But this time around, I'm craving something deeper, something more hands-on.

So, I jumped into the 'NLP with Hugging Face' course that's been buzzing in the circles I follow. It's one thing to hear about it, but quite another to experience it firsthand. Diving into Chapter 1 was like opening a new door in a house I thought I knew well. Sure, I've always been comfortable with the nuts and bolts of Attention mechanisms, playing around with Query, Key, and Value. But what I'm after now is a bird's-eye view – understanding these concepts not just at a technical level but how they fit into the bigger picture of NLP.

It's more than just brushing up on skills; it's about widening my lens in NLP, getting a grip on the subtle art of using Hugging Face's models to craft something truly innovative. It's exciting, a bit daunting, but mostly exhilarating to see where this journey takes me.

