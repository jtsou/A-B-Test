# A/B Test

<h2>Experiment Overview</h2>
<p>
Udacity courses currently have two options on the home page: “start free trial” and “access
course materials”. If the students click ‘start free trial’, they will be asked to enter their credit
card information, and then they will enroll in a free trial for a paid version. After 14 days, they
will automatically be charged unless the students canceled first. If the students click on “access
course materials”, they will be able to view the videos and take the interactive quizzes for free,
but they will not receive a verified certificate or one-on-one coaching support, moreover, they
will not be able to submit their final projects and get feedbacks for them.
In this experiment, Udacity tested a change where if the student clicked “start free trial”, they
were asked how much time they had available to commit to the course. If the students have 5 or
more hours per week, they would go through the registration process as usual. However, if not;
a message would appear indicating that Udacity course usually require a greater time
commitment for successful completion. Students will also be told that they can access the course
materials for free.
The hypothesis for this experiment was that this might set a clear expectation for students
upfront, thus reducing the number of frustrated students who left the free trial because they did
not have enough time for the course- without significantly reducing the number of students to
continue past the free trial and eventually complete the course. If this works, Udacity could
improve the overall student experience and improve the counseling’s capacity to support
students who are likely to complete the course.
</p>

<h2>Experiment Design</h2>
<h3>Metric Choice</h3>
<p>
Invariant Metric: Number of cookies, Number of clicks, Click-through-probability
Valuation Metric: Gross Conversion, Net Conversion, Retention

<ul>
<li> Number of cookies: Good invariant metric because number of cookies is not going to be
affected by the change that company is launching at the time of enrollment.</li>
<li> Number of user-ids: Not a good invariant nor evaluation metric. Since the enrollment
might depend on the ‘start free trial' page, we could expect to see different values in
control and experiment group. Therefore, it can’t be invariant. It is not a good evaluation
metric because it is reductant to other metrics such as gross conversion. Gross
conversion is a fraction of user-id and using gross conversion is a better choice.
<li> Number of clicks: Similar to number of cookies. Good invariant metric because the clicks
happen before the user sees the page before they decide to click on the button.</li>
<li> Click-through-probability: invariant metric. Again, since the users have not seen the page we
tested on before they decide to click the button, the click-through-probability also does not
depend on our test and is a good invariant metric.</li>
<li> Gross conversion: Not a good invariant metric because the number of users who enroll in
the free trial is dependent on the experiment. Good evaluation metric because it is
directly dependent on the effect of the experiment and allows us to show whether we
managed to decrease the cost of enrollments that aren’t likely to become paying
customers.</li>
<li> Retention: Not a good invariant metric because the number of users who enroll in the
free trial is dependent on the experiment. Good evaluation metric because it is directly
dependent on the effect of the experiment, and shows positive financial outcome of the
change.</li>
<li> Net conversion: Not a good invariant metric because the number of users who enroll in
the free trial is dependent on the experiment. Good evaluation metric because it is
directly dependent on the effect of the experiment, and shows positive financial outcome
of the change.</li>
</ul>
I will look at both Gross Conversion and Net Conversion. The gross conversion will show us
whether we lower our cost by introducing new pop up. Net conversion will show how the change
affects our revenue. After the experiment, we should expect that gross conversion have a
significant decrease, and net conversion should not decrease significantly.
</p>
<h2>Measuring Standard Deviation</h2>
<p>
To determine whether the analytical estimates of standard deviation are accurate, such as whether it
matches the empirical standard deviation, we consider whether or not the unit of analysis and unit of
diversion matches up.
Using the online calculator, we calculated number of samples required as following:
For 5000-page view:
<ul>
<li>number of clicks = 5000 × 0.08 = 400</li>
<li>number of enrollment = 5000 × 0.08 × 0.20625 = 82.5</li>
</ul>
Baseline table:
<table style="width:100%">
  <tr>
    <td>Unique cookies to view page per day</td>
    <td>40000</td>
  </tr>
  <tr>
    <td>Unique cookies to click “Start free trial” per day</td>
    <td>3200</td>
  </tr>
  <tr>
    <td>Enrollments per day</td>
    <td>660</td>
  </tr>
   <tr>
    <td>Click-through-probability on “Start free trial”</td>
    <td>0.08</td>
  </tr>
   <tr>
    <td>Probability of enrolling, given click</td>
    <td>0.20625</td>
  </tr>
    <tr>
    <td>Probability of payment, given enroll</td>
    <td>0.53</td>
  </tr>
      <tr>
    <td>Probability of payment, given click</td>
    <td>0.1093125</td>
  </tr>
</table>

<table style="width:100%">
  <tr>
    <th>Metric</th>
    <th>Value</th> 
    <th>Std</th>
    <th>Std /5000</th>
    <th>Probability</th>
  </tr>
  <tr>
    <td>Gross conversion</td>
    <td>0.2063</td>
    <td>0.0072</td>
    <td>0.0202</td>
    <td>0.0800</td>
  </tr>
  <tr>
    <td>Retention</td>
    <td>0.5300</td>
    <td>0.0194</td>
    <td>0.0549</td>
    <td>0.0165</td>
    
  </tr>
  <tr>
    <td>Net conversion</td>
    <td>0.1093</td>
    <td>0.0055</td>
    <td>0.0156</td>
    <td>0.0800</td>
  </tr>
</table>

<ul>
<li>Gross Conversion: The unit of diversion = unit of analysis. Analytical estimate of Standard
Deviation tends to be empirical estimate of Standard Deviation.</li>
<li>Retention: Retention unit of diversion is not the same as unit of analysis.</li>
<li>Net Conversation: The unit of analysis and unit of diversion are both the same for "gross
conversion" metric, and the analysis directly applies here. The analytical estimate is expected to
be mostly accurate, but collecting more data to verify if one has time will be even better.</li>

<h2>Sizing</h2>
<h3>Number of Samples vs. Power</h3>
<p>
I want gross conversion significantly decrease AND net conversion does not significantly decrease.
I will not use Bonferroni as it is too conservative. I want all my metrics to be significant.
α = 5%, β = 20% </p>

<ul>
<li>Gross Conversion (base conversion rate= 20.625%, dmin=1%)</li>
<li>Retention (base conversion rate=53%, dmin=1%)</li>
<li>Net conversion (base conversion rate=10.93125%, dmin=0.75%)</li>
</ul>

<table style="width:100%">
  <tr>
    <th>Metric</th>
    <th>Pageviews</th> 
    <th>Sample size(clicks)</th>
  </tr>
  <tr>
    <td>Gross conversion</td>
    <td>322,937</td>
    <td>25,835</td>
  </tr>
  <tr>
    <td>Retention</td>
    <td>2,370,606</td>
    <td>39,115</td>
  </tr>
  <tr>
    <td>Net conversion</td>
    <td>342,662</td>
    <td>27,413</td>
  </tr>
</table>

We need pageviews:
<ul>
<li>Gross Conversion: 25835 x 40000 / 3200 =322,937</li>
<li>Retention: 39115 x 40000 / 660 = 2,370,606</li>
<li>Net conversion: 27413 x 40000 / 3200 = 342,662</li>
</ul>

<h3>Duration vs. Exposure</h3>
<p>First trial (Use Gross Conversion, Retention, and Net Conversion as evaluation metrics):
<ul>
<li>Number of page views = 2370606 x 2 = 4741212 (because two groups)</li>
<li>Fraction = 1.0</li>
<li>Days = 4741212 / 1 / 40000 = 118</li>
</ul>
First trial requires 118 days to do. This is way too long.</p> 
Second trial (only Gross Conversion and Net Conversion as evaluation metrics):
<ul>
<li> Number of page views = 342662 x 2 = 685324 (because two groups)</li>
<li>Fraction = 1.0</li>
<li>Days =685324 / 1/40000 = 18</li>
</ul>
<p>
Second trial requires 18 days to do.
Experiment of 18 days is short enough, so we would choose Gross Conversion and Net Conversion as
evaluation metrics.
In this experiment, when students want to enroll, we ask how much time they are willing to commit for
the course they want to enroll and recommend students not to enroll if they could not investigate more
than 5 hours time. This option works for student as those who don’t have enough time could choose to
access course materials, do quizzes, or watch videos whenever. In addition, when they decide to enroll,
they could do it at any time. We also do not ask personal information in this experiment so privacy is not
an issue. This experiment does not affect the database nor the design of the website so the website is not
harmed by the experiment, either. Fraction of 1.0 is chosen because if we decrease the fraction of traffic,
we would need more time to run this experiment, and 18 days isn’t particularly short either. 
</p>

<h2>Experiment Analysis</h2>
<h3>Sanity Checks</h3>
<table style="width:100%">
  <tr>
    <th></th>
    <th>Control Group</th> 
    <th>Experiment</th>
  </tr>
  <tr>
    <td>#pageview</td>
    <td>345543</td>
    <td>344660</td>
  </tr>
  <tr>
    <td>#clicks</td>
    <td>28378</td>
    <td>28325</td>
  </tr>
</table>

<table style="width:100%">
  <tr>
    <th>Metric</th>
    <th>Lower Bound</th> 
    <th>Upper Bound</th>
    <th>Observed Value</th>
    <th>Result</th>
    
  </tr>
  <tr>
    <td># of Cookies</td>
    <td>0.498820392149</td>
    <td>0.501179607851</td>
    <td>0.5006396669</td>
    <td>PASS</td>
  </tr>
  <tr>
    <td># of Clicks</td>
    <td>0.495884957</td>
    <td>0.5041155043</td>
     <td>0.5004673473</td>
    <td>PASS</td>
  </tr>
  <tr>
    <td>Click through
Probability</td>
    <td>0.08121035975</td>
    <td>0.0830412674</td>
     <td>0.08212581357</td>
    <td>PASS</td>
  </tr>
</table>

<h2>Result Analysis</h2>
<h3>Effect Size Tests</h3>
<p>95% Confidence interval around the difference between the experiment and control group for evaluation
metrics.</p>

<table style="width:100%">
  <tr>
    <th>Metric</th>
    <th>dmin</th>
    <th>Lower Bound</th> 
    <th>Upper Bound</th>
    <th>Statistical
Significant</th>
    <th>Practical
Significant</th>
    
  </tr>
  <tr>
    <td>Gross
Conversion</td>
    <td>1%</td>
    <td>-0.0291</td>
    <td>-0.0120</td>
    <td>TRUE</td>
    <td>TRUE</td>
  </tr>
  <tr>
    <td>Net
Conversion</td>
    <td>1%</td>
    <td>-0.0116</td>
    <td>0.00185</td>
    <td>FALSE</td>
    <td>FALSE</td>
  </tr>
</table>
<ul>
<li>Gross Conversion is both Statistically Significant and Practical Significant</li>
<li>Net Conversion is neither Statistically Significant and Practical Significant</li>
</ul>

<h3>Sign Tests</h3>
<table style="width:100%">
  <tr>
    <th>Metric</th>
    <th>p-value</th>
    <th>Statistically Significant</th> 
  </tr>
  <tr>
    <td>Gross Conversion</td>
    <td>0.0026</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Net
Conversion</td>
    <td>0.6776</td>
    <td>No</td>
  </tr>
</table>

<h3>Summary</h3>
<p>Bonferroni correction is not used here because our launch decision is based upon two metrics, Gross
Conversion and Net Conversion. To launch, we need both the metrics to meet the expectations; that is,
we want gross conversion significantly decrease AND net conversion does not significantly decrease.
Bonferroni correction is suitable when it is applied to ‘OR’ situation. There were no discrepancies
between the effect size hypothesis tests and the sign tests.</p>

<h2>Recommendation</h2>
<p>Based on the analysis, gross conversion turned out to be negative and practically significant. This is good
because this decrease the costs by discouraging trial signups that are unlikely to convert. Net conversion,
however, ended up being statistically and practically insignificant. Refer to the illustration above, the
confidence interval includes the negative practical significance boundary. That is, it’s possible that this
number went down by an amount that would matter to the business. This means that there is a risk that
the introduction of the trial screener may lead to a decrease in revenue. This is not an acceptable risk to
launch.
This experiment makes me consider testing other designs of the screener before we decide whether to
release the feature.</p>

<h2>Follow-Up Experiment</h2>
<p>
Goal of a company is to earn money by satisfying customers. In this experiment, we tried to filter out the
users who are going to enroll to trial but are not going to spend a lot of time on studying.
In follow-up experiment, we can perform another experiment by changing the number of hours from
screener to prerequisite knowledge required to start the course. This screen aims to help students to get
an idea about what knowledge they should have before joining Udacity course. If the students don’t have
the knowledge, then the screen should suggest them to go to the suggested courses that are listed in
prerequisites and can join those courses.
Null Hypothesis: No significant difference between control and experiment group.
Unit of diversion: Cookie
For testing this hypothesis, we have to measure number of cookies, number of clicks, number of
enrollments, and number of payments. From those, we can calculate Gross Conversion & Net Conversion.
If Gross Conversion & Net Conversion will result to be statistically and practically significant then we will
be able to launch our test.
</p>

<h5>References</h5>
<ul>
<li><a href='https://rpubs.com/superseer/ab_testing'>https://rpubs.com/superseer/ab_testing</a></li>
<li>Udacity A/B Test</li>
<li>Udacity Discussion Forum</li>
</ul>
