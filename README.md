# Customer Segmentation using R

- Customer Segmentation is one of the most important applications of unsupervised learning. Using clustering techniques, companies can identify several segments of customers allowing them to target the potential user base. In this machine learning project, we will make use of K-means clustering which is the essential algorithm for clustering unlabeled datasets.

# What is Customer Segmentation?
- Customer Segmentation is the process of dividing of the customer base into several groups of individuals that share a similarity in different ways that are relevant to marketing such as gender, age, interests, and miscellaneous spending habits.

- Companies that deploy customer segmentation are under the notion that every customer has different requirements and requires a specific marketing effort to address them appropriately. Companies aim to gain a deeper approach to the customer they are targeting. Therefore, their aim has to be specific and should be tailored to address the requirements of each and every individual customer. Furthermore, through the data collected, companies can gain a deeper understanding of customer preferences as well as the requirements for discovering valuable segments that would reap them maximum profit. This way, they can strategize their marketing techniques more efficiently and minimize the possibility of risk to their investment.

- The technique of customer segmentation is dependent on several key differentiators that divide customers into groups to be targeted. Data related to demographics, geography, economic status as well as behavioral patterns play a crucial role in determining the company's direction toward addressing the various segments.

# Five types of customer segmentation:

- Demographic Segmentation: This segmentation divides the customer market based on gender, age, occupation, etc.
- Geographic Segmentation: This segmentation divides the customer market based on country, state, city, and locality.
- Technographic Segmentation: This segmentation divides the customer market on the basis of apps, software, and devices.
- Psychographic Segmentation: This segmentation divides the customer segmentation on the basis of attitudes, values, and personal traits.
- Behavioral Segmentation: This kind of segmentation divides the customer market on the basis of actions, spending habits, and how they consume.


# Benefit of Customer Segmentation for Business:
1. More Customer Retention
    - Customer retention permits you to gain proficiency with an extraordinary arrangement about your clients so you can take into account their necessities all the more proficiently.  A one-on-one association with your clients will assist you with winning fulfilled clients. You can likewise tailor your correspondence relying upon the client lifecycle.

2. Enhances Competitiveness
    - The better your customer retention is, the more revenue you are likely to achieve. When a business scores a good customer segmentation along with better utilization of its showcasing financial plans, it acquires a serious edge over opponent organizations. On the off chance that you section up your market, you are not able to your clients and as needs are.

3. Establishes Brand Identity
    - Distinguishing your image will assist your clients with straightforwardly captivating your items. Whenever you have distinguished the vital helpers for your client, for example, plan or cost or user requirements, you can mark your items properly. By dividing your clients, you can make them very much aware of your image.

4. Better Customer Relationship
    - Breaking down a huge client base into more reasonable pieces, making it simpler to distinguish your intended interest group and dispatch missions to the most significant individuals, utilizing the most important channel. This creates a good customer relationship as they feel welcomed and heard.

5. Leads to Price Optimization
    - No business is successful without a good customer base. In order to have one, you need to cater to their primary issues like what their income range is while setting a price for a particular product. This is what price optimization is. The better suited your product price range is according to a customer’s budget, the more your customers will buy it.

6. Best Economies of Scale
    - Economies of scale is a position where you can reach your specific goal at the minimum cost possible. This can be done through efficient customer segmentation as it helps divide customers into different segments and later, you can focus on limited resources being cost-effective.

7. Improves Channel of Distribution
    - Customer segmentation can help with distinguishing where clients shop and when can educationally shape item dissemination systems, for example, what sort of items are sold at specific outlets. This will eliminate disarray among your colleagues about whom they need to convey the item and at what time.

8. It Allows You to Fine-Tune Your Message
    - Dividing customers into segments can actually help you identify what kind of audience you are targeting and hence, can help you deliver your message accordingly. One way to convert visitors into customers is by grabbing their attention and this can be done through customer segmentation.

9. Increases Your Revenue
    - During the way toward gathering your clients into groups, you may find that you have recognized another market portion, which could thus adjust your advertising center and procedure to fit. This channel of ideas from customer preferences is what will help you convince them to buy your product hence generating a greater portion of revenue for you.

10. Increases Brand Awareness
    - Customizing marketing correspondence for clients prompts a superior connection between the client and the business. This can significantly improve client devotion. Recognizing your client as beyond what another individual from your email data set can go far for your image value.


Reference: [Understanding the Benefits of Customer Segmentation](https://bython.com/benefits-of-customer-segmentation/)

# Gap Statistic Method
- Abstract The Gap statistic is a standard method for determining the number of clusters in a set of data. The Gap statistic standardizes the graph of log(Wk), where Wk is the within-cluster dispersion, by comparing it to its expectation under an appropriate null reference distribution of the data.
- The gap statistic has been published by [R. Tibshirani, G. Walther, and T. Hastie (Standford University, 2001)](http://web.stanford.edu/~hastie/Papers/gap.pdf).
- The ‘gap statistic’ for estimating the number of clusters (groups) in a set of data. The technique uses the output of any clustering algorithm (e.g. K-means or hierarchical), comparing the change in within-cluster dispersion with that expected under an appropriate reference null distribution.
- Clustering is an important technique in Pattern Analysis to identify distinct groups in data. Due to data being mostly more than three-dimensional, we perform dimensionality reduction methods like PCA or Laplacian Eigenmaps before applying a clustering technique. The data is then available in 2D or 3D and this allows us to visualize the found clusters very nicely to humans.

### K-Means

- K-Means performs three steps. But first you need to pre-define the number of K. Those cluster points are often called Centroids.

    1) (Re-)assign each data point to its nearest centroid, by calculating the euclidian distance between all points to all centroids.

    2) Calculate the mean for each centroid based on all respective data points and move the centroid in the middle of all his assigned data points.

    3) Go to 1) until the convergence criterion is fulfilled. In my case, I calculate the within-cluster distance between all points to the re-assigned centroid mean. After a new iteration, if all centroids together moved less than 0.01, so basically nothing happens anymore, the convergence criterion is performed.


### Gap Statistic
- Even if Gap-Statistics is a good approach to finding a suitable K, it is still not perfect. For example, we needed to introduce a new hyperparameter, namely the number of K for which the W_uniform is simulated on. We can’t be sure what the ideal value for this is. Furthermore, the random initialization of the centroids can lead to an over- or underestimation of K*.

- But by knowing all of the aspects of Gap-Statistics, the best is to apply it and then run the Gap-Statistic plot a couple of times. Taking the average of the Gap-Statistics can be an increased evaluation criterion.

Reference: [K-means Cluster Analysis](https://uc-r.github.io/kmeans_clustering#gap)

- We can use Gap Statistic Method for any of the clustering methods like K-means, hierarchical clustering, etc. Using the gap statistic, one can compare the total intracluster variation for different values of k along with their expected values under the null reference distribution of data. With the help of Monte Carlo simulations, one can produce the sample dataset. For each variable in the dataset, we can calculate the range between min(xi) and max (xj) through which we can produce values uniformly from interval lower bound to upper bound.

- For computing the gap statistics method we can utilize the clusGap function for providing gap statistics as well as standard error for a given output.
