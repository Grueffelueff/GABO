# GABO
predicting the winner of the Great Australian Bake Off

### The motivation
Inspired by [this guthub Repo](https://github.com/dantaki/DeepBake) by *dantaki*, which was sent to me by my boyfriend, who worries that my obsession with baking and everything concerning the bake off is taking overhand, I decided to redo his analysis. But since there's not much fun in just redoing absolutely the same, I decided to go with the Great Australian Bake Off instead of the Great British Bake Off. 

On the pro-side this will probably get some different results and it could be interesting to compare them afterwards and there's also a new season starting in two weeks time, so not long to wait, until the algorithm can be tested in a "real life setting".
On the con-side, the Australian counterpart of the show has only run for 4 seasons until today. So setting one season aside for testing, we'll have just the data from 3 seasons to find our algorithm.

Same as *datanki* I'll get my data from the [wikipedia page](https://en.wikipedia.org/wiki/The_Great_Australian_Bake_Off) of the Great Australian Bake Off. 
Until now there have been 4 seasons. Season 1 consisted of 10 bakers and 8 episodes, while seasons 2, 3 and 4 featured 12 bakers and 10 episodes in total.
Since the show has evovled somewhat over time (different judges and hosts for instance) we'll take season 3 as testset. The main reason for this is that I believe  season 4 should be used to tune the model, since it is the "closest" to the upcoming season 5. I don't want to use either season 2 or season 1 for testing, since especially season 1 has been a bit different to the other ones. 

### The approach
As mentioned, I'll get the data from the wikipedia page.
I'll then use the caret package to try to find a working classification algorithm that predicts the ranking of a contestant based on two things:

- The performance in the most recent episode and
- the averaged performance in all previous episodes

So in the end, after each show we can feed the algorithm the latest scores and hopefully get a decent prediction as to who is going to win this years bake off and additionally who will make it to the finale.

We'll train the model on the data of seasons 1, 2 and 4 and use season 3 as validation set. After we found the right model, we'll retrain the model using all 4 seasons in the hope of having an even better prediction model for the upcoming season 5.


