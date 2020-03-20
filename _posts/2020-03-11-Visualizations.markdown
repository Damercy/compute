---
layout: post
title: Visualizations
date: 2020-03-11 20:00:00 +0530
permalink: /:title
---
We have this subject in our course called __`Big Data`__ and it's pretty awesome. My interest in the subject grew significantly in the last lab and that's because of visualizations. Let me explain.

First, an introduction to the subject. Big Data, as the name suggets, loosely translates to dealing with large volume of data. There are other factors like variety, veracity, value etc. to qualify a dataset as Big Data, but let's just keep it simple for now. A large amount of data (imagine petabytes, zetabytes, yottabytes) requires specialized methods because it's tough to manage such huge data in local machines without messing up.

The specialized methods that is coherent with Big Data include cloud computing technology to store data at different clusters, Streaming data management technology, Splitting-Mapping-Reducing data services like MapReduce and so much more. I don't want to use the technical jargons that surround Big Data because neither of us are worthy enough to understand deeply about them, so let's just pretend we have heard of them. (In case you haven't, just spit out random terms like MapReduce, Spark, Apache Kafka, Veracity, GCP etc. and you'll find yourself as a BigData pseudo-expert among the masses)

Second, why use Big Data? The simple answer is ...`why not?` As I like to see it,with time, people are merely turning into consumers and few actually care about creating _something_ (producers). These consumers are constantly consuming content (online) which the producers produce. This symbiotic cycle of production-consumption leads to data as a by-product and my my, is it big. It's __HUGE!__ So computer engineers are interested in using this by-product(data) to enhance their applications so that the consumers are hooked on to their consumption-device for much longer, ideally never breaking the cycle of consumption resulting in a constant flow of money to the developers (businessmen).

I know, maybe it's not as __dark__ as it sounds but this is just my view.

Third, what made me like this subject are the visualizations. You see, one of the key steps to extract insights from raw data is to visualize it in the first place. There are numerous awesome tools out there for use, and we used the `seaborn module` in python in our last lab.

Let's see what we did.

### Problem: Extract insights from the raw Boston Dataset

Let's see what the [Boston dataset][kaggle-site] contains.

![img](/compute/images/boston-dataset.JPG "Welcome to Boston!")

The dataset has 506 rows and 14 columns. The above picture is just the first 5 rows. Ignore the extra 'Unnamed' column (rightmost) henceforth. It isn't included in the dataset.

The columns are known as attributes. Thus, `crim`,`zn`,`indus`,`nox` etc. are all attributes of the boston housing dataset. These are the _`variables`_ we will work with to predict and visualize!
(Please keep in mind that the attributes are alias names and not the complete names. Thus, nox means the nitrogen oxides concentration (ppm) in the atmosphere, dis represents weighted mean of distances to five Boston employment centres and so on.)

Now let's find a quick co-relation between each of the attributes.

![img](/compute/images/correlation.JPG "Relationships are all that there is.")

Now, don't be overwhelmed! It's easy. It is.

Notice closely and you'll see that the right diagonal of the above matrix have the same value of __1.0000000__. It means that the corresponding row and column are completely related to each other and so, for __per unit change in the x-axis__, there is a 1.00000000 __per unit change in the y-axis__, which again just means, if you change a value in the x-axis then the y-axis changes with the same offset as well. Thus, each attribute is completely = 1.000000 = 100% correlated to itself!

Notice the other numbers now. Some have postive values while some have negatives. the way I like to see it is as follows:
> sign --> +ve/-ve slope  
> number --> for per unit change of x, how much change in y i.e. correlation

For example, consider the row `nox` and column `dis`. The value is -0.769230. The value says that nox and dis are 76.92% related to each other while the sign says it's a negative slope = there's an inverse relationship = as the dis increases, nox decreases.

If you've read it till here, please tell me you find this __cool__. Isn't it so cool?! We see at signs and values and we can `infer fuckin' universes`! Okay, maybe not universes, but atleast we can visualize the relationships. And that's cool!

To finish off, let's add some color to our above matrix to help with visualization.

![img](/compute/images/viz.JPG "Born-in-Sea aka Seaborn module")

The above matrix is _still_ the same, except there's colors (as if you couldn't see). We're interested in the __brightest__ and __darkest__ region as the brightest color (white) represents a greater correlativity while the darkest color (black) represents an inverse correlativity. You can even forget the values that are connotated in the above picture because we can easily visualize the relationships between different attributes from the colors itself! And this is _amazing_ to me. It is so, so cool!

This article's getting too long. I must stop. And I did.

Thanks for reading!

[kaggle-site]:https://www.kaggle.com/c/boston-housing