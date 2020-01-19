---
title: 'Ask About Generics: ProPublica Study Shows Doctors That Take Industry Payments Prescribe
  More Brand Name Drugs'
author: Noah Stafford
date: '2020-01-18'
slug: ask-about-generics-study-shows-doctors-that-take-industry-payments-prescribe-more-brand-name-drugs
categories: []
tags: []
---

This really isn't a post intended as a persuasive essay to get people to buy generic drugs, but I'll start with a little bit on that because it's an important discussion to have.  

If you are prescribed medication, and there is a generic option, ask for that generic version at the pharmacy.  If your doctor mandates that you use the brand-name version, ask them why.  
<div style="width:50%; height:50%; font-size:80%; float:right;"><img src="/img/pill_man.jpg" alt="The Pill Man" width="width" height="height" style="padding-bottom:0.5em;" />This friendly face could be laughing all the way to the bank to cash tens of thousands in big pharma payouts at YOUR expense.  But is he?</div>

The simple truth is that generic drugs are not worse.  They are cheaper than the brand-name, because the brand-name enjoyed patent protection, and used that monopoly on the marked to charge more for the drug.  When the patent expires, the drug is then open to be manufactured by any company, and these drugs are usually sold at a much lower price.  Yet doctors continue to prescribe (and people continue to ask for) brand-name drugs well after generics are available.  Why? On reason is that there is an unearned stigma around generics.  American advertising likes to tell us that there is something special and unique about branded products.  There are people out there, right now, making a living off of their ability to [distinguish authentic Adidas Yeezys from fakes](https://youtu.be/X3ySrcI2mEA).  The difference between brand-name and generic is not like the difference between Adidas and Sketchers.  It would be more like the difference between Adidas and Adidas made in another factory.  As Patrick J. Skerrett states in a post on the Harvard Health Blog [^1]

_Generic drugs are chemical clones of their brand-name counterparts. By law, a generic drug must_
1. _contain the same active ingredients as the brand-name drug_
2. _be identical in strength, dosage form, and administration_
3. _work the same way in the body (be bioequivalent)_
4. _meet the same standards for identity, strength, purity, and quality_
5. _be made by the same rules the FDA has set for the brand-name drug._


[Follow this link](https://www.health.harvard.edu/blog/generic-drugs-dont-ask-just-tell-201301075766) for Patrick J. Skerrett's much more informed and complete discussion of this issue.

***

Now that that's out of the way, what I really want to discuss here is ProPublica's investigation into the relationship between industry payments to doctors, and those doctors' tendency to prescribe brand-name drugs.  The research merged two different datasets.  The first normal Medicare Part D data, which tracks the medications prescribed by doctors.  The second is a new dataset created due to mandates in the Affordable Care Act.  Pharmaceutical and medical device companies are now required to report payments to doctors, which is released through the federal open payments database, and has been cleaned and annotated by ProPublica.  Their data can be searched by doctor using their [dollars for docs tool](https://projects.propublica.org/docdollars/)[^3] and can be purchased for stupid sums of money[^4].  These datasets were merged and analyzed in a [ProPublica paper](www.propublica.org/article/doctors-who-take-company-cash-tend-to-prescribe-more-brand-name-drugs) titled "Matching industry payments to Medicare prescribing patterns: an analysis."[^5].

The investigators limited their sample to the top five most common categories of physicians.  Family medicine physicians, internal medicine physicians, cardiologists, psychiatrists, and ophthalmologists were kept in the sample, for a total of 150,323 physicians.  Using the Medicare data, the percentage of brand-name claims out of total claims was calculated for each doctor.  These percentages were then normalized[^6] relative to the mean percentage and standard deviation within each specialty, controlling for the large differences in mean rates between the specialties.  Ophthalmologists, specifically, were noted as having a much higher percentage of brand-name prescrption claims in general.  Physicians with brand-name prescription rates greater than one standard deviation from the mean using this method were considered 'high brand-name prescribers".  

So what they end up with is a binary 'high brand-name prescriber' variable and a binary 'received any payments from industry' variable.  They note that the percentage of doctors who received payments ranged between ~70 and 87 percent among the specialties.

These variables allowed the investigators to calculate risk ratios[^7].  In this case, the risk ratios are interpreted as the ratio of the probability of being a high brand-name prescriber given the doctor received industry payments to the probability of being a high brand-name prescriber given the doctor did not receive any industry payments.

As indicated in the "RR" column of Table 3, doctors that receive industry payments are 2 to 3 times more likely to be among the group of high-rate brand-name prescribers within their field.  All these statistics are significant at the 5% level.
<img src = "/img/table_3_propublica_payments.png" style="max-width:90%;min-width:50%;" alt="Table 4"/>

The investigators' analysis takes this basic framework and spins it in a number of different ways, looking at the results' sensitivity to defining their two derived variables, but they consistently get the same result

In a second section of the analysis, they demonstrate when you slice up the amount of money doctors received and bucket them, you see a clear, steady increase in the brand-name prescribing rate as the amount of money received increases.

<img src = "/img/table_6_propublica_payments.png" style="max-width:90%;min-width:50%;" alt="Table 6"/>

There are some deficiencies in the investigators' approach to the modeling in this study.  Instead of finding a model that is appropriate for their data, they approached the problem from the other direction, deriving features from their data that could be analyzed with models they knew how to employ.  Their results are still sound -- their sensitivity analysis was thorough enough to convincingly argue that their significant results were not due to random variation or an opportunely chosen threshold in their feature derivation.  However, this approach makes me hesitant to trust the values of the risk ratios they calculated as anything more than an artifact of their chosen methods.  The investigators avoid making strong conclusions about effect size, mostly just claiming a significant result.  

I would be interested in seeing the results of a logistic regression approach to this hypothesis.  The same RR based analysis could be replicated with RR derived from a logistic regression[^9]. The doctors could have been modeled as random effects in order to control for the between-doctor variation of patient demographics, and the model would allow for the use of other covariates to adjust for the demographics of each doctor's patient population.

I think the largest issue with this study is how it defines the brand-name prescription rates.  All brand-name drugs are counted in this measure, full stop.  Of course, some brand-name drugs have to be prescribed, since their patents have not expired and they are the only available option for treatment.  As the measure stands, it is possible that a large portion of the variation can be attributed to each doctor's patient demographics.  Doctors with more patients with conditions that demand brand-name medications will naturally have higher brand-name prescription rates.  Looking only at prescription rates for brand-name drugs that have generic alternatives would perhaps cut closer to the core of the question looking to be answered, though this might cause the sample size for each doctor to get too small.

The investigators are clear to note that this study is an associative study and make no claims about causation.  I think that this is important to discuss.  The implication of this study is that doctors are being influenced by industry money to prescribe more expensive, branded medication against their patients' financial interests.  This is in no way proven by this study, or really even tested.  All that can be said is that the data demonstrates that an association exists which could have a number of causes, one of which is the former.  Doctors could be prescribing brand-name medication due to industry influence, but the reverse could also be true -- pharmaceutical companies could be hiring doctors who like to use their medications, because they value their working knowledge of the product.  As previously discussed, the demographics of the patient populations are not adjusted for, and if doctors that receive more industry money also tend to treat patient with conditions that require brand name drugs, this could also explain the observed effect.  

As more data comes in over the years, revisiting this analysis would be worthwhile.  A larger dataset would enable investigators to make more powerful inferences, and more effectively control for covariates.  The use of more complex modeling and more precisely defined variables would be worthwhile in improving the ability of the modeling the answer the question being asked.

This study is finding a very interesting signal from an interesting new dataset.  The questions being asked with the data are really interesting, and there's plenty more on this general subject on ProPublica, where this study lives as part of on ongoing series investigating the [ties between doctors and medical companies](https://www.propublica.org/series/dollars-for-docs)[^8].


[^1]: Skerrett, Patrick J. “Generic Drugs: Don't Ask, Just Tell.” Harvard Health Blog, 7 Jan. 2013, www.health.harvard.edu/blog/generic-drugs-dont-ask-just-tell-201301075766.

[^2]: Jones, Ryann Grochowski, and Charles Ornstein. "Matching industry payments to Medicare prescribing patterns: an analysis." Internet Document: Mar (2016).

[^3]: https://projects.propublica.org/docdollars/

[^4]: https://www.propublica.org/datastore/dataset/dollars-for-docs

[^5]: Ornstein, Charles, et al. “Now There's Proof: Docs Who Get Company Cash Tend to Prescribe More Brand-Name Meds.” ProPublica, 9 Mar. 2019, www.propublica.org/article/doctors-who-take-company-cash-tend-to-prescribe-more-brand-name-drugs.

[^6]: https://en.wikipedia.org/wiki/Standard_score#Calculation

[^7]: https://en.wikipedia.org/wiki/Relative_risk#Inference

[^8]: https://www.propublica.org/series/dollars-for-docs

[^9]: https://cran.r-project.org/web/packages/logisticRR/vignettes/logisticRR.html