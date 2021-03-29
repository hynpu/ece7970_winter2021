# Citation
Rodriguez, I., Manfré, A., Vella, F., Infantino, I., & Lazkano, E. (2019). Talking with Sentiment: Adaptive Expression Generation Behavior for Social Robots. Advances in Intelligent Systems and Computing, 855, 209–223. https://doi.org/10.1007/978-3-319-99885-5_15

# Abstract
In this paper, the author proposed a learning based approach (GAN) to generate emotional liked gestures on a robot, based on on sentiment processing, including head posture, voice tune, eye color, and etc.

The author proposed that the gestures, postures, and movements of the body and face expressions are used to convey information about the emotions and thoughts of the sender while supporting verbal communication.

To generate the gesticulation movement, there are mainly three steps:

1. Extract the sentiment from the text using VADER sentiment analyzer. The sub-systme will analyze the polarity and the intensity of sentiments expressed.

2. Sentiment to emotion conversion by identifying the emotion polarity of the conversation (happy, sad, or neutral)

3. Generate the appropriate expression using GAN. The sub-system takes as input the emotion value obtained from the “Emotion Selector” and produces a number of gestures that are well suited to be executed with the right velocity according to the speech duration.

From the generated emotion, the robot will have the following gestures:　head tilt (upwards, downwards or straight), eye color  (blue for sad, or yellor for happy), and voice intonation (chaning the pitch and speed rate)

# Spotlight

This paper has a pretty interesting topic, which uses the GAN to generate the robot emotion gesture. The research outcome can be used in our project, to better deal with the *persuasive stragety* mentioned in Dr. Louie's paper.

# What to learn 

How to train the GAN? What will be used as the input dataset for training