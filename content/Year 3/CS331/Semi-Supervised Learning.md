> SSL attempts to solve the issues that [[Supervised Learning]] relies on time consuming data labelling and that [[Unsupervised Learning]] may not always provide accurate results.

Essentially, by having access to a small set of labelled data and a large corpus of unlabelled data, a model can be trained quicker than by using SL and more accurately than using USL.

However, it relies upon two key assumptions:
- Data points close together are likely to have the same label (**continuity**).
- Data points within a **cluster** are likely to have the same label.