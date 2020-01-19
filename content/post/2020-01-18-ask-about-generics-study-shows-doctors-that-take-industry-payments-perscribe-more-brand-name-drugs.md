---
title: 'Ask About Generics: Study Shows Doctors That Take Industry Payments Perscribe
  More Brand Name Drugs'
author: Noah Stafford
date: '2020-01-18'
slug: ask-about-generics-study-shows-doctors-that-take-industry-payments-perscribe-more-brand-name-drugs
categories: []
tags: []
---

This really isn't a post intended as a persuasive essay to get people to buy generic drugs, but I'll start with a little bit on that because it's an important discussion to have.  If you are perscribed medication, and there is a generic option, ask for that generic version at the pharmacy.  If your doctor mandates that you use the brand-name version, ask them why.  

Generic drugs are not worse.  They are cheaper than the brand-name, because the brand-name enjoyed patent protection, and used that monopoly on the marked to charge more for the drug.  When the patent expires, the drug is then open to be manufactured by any company, and these drugs are usually sold at a much lower price.  Yet doctors continue to perscribe (and people continue to ask for) brand-name drugs well after generics are available.  Why? On reason is that there is an unearned stigma around generics.  American advertising likes to tell us that there is something special and unique about branded products.  There are people out there, right now, making a living off of their ability to [distinguish authentic Adidas Yeezys from fakes](https://youtu.be/X3ySrcI2mEA).  This is not the case with generic drugs.  As Patrick J. Skerrett states in a post on the Harvard Health Blog [^1]

_Generic drugs are chemical clones of their brand-name counterparts. By law, a generic drug must_
1. _contain the same active ingredients as the brand-name drug_
2. _be identical in strength, dosage form, and administration_
3. _work the same way in the body (be bioequivalent)_
4. _meet the same standards for identity, strength, purity, and quality_
5. _be made by the same rules the FDA has set for the brand-name drug._


[Follow this link](https://www.health.harvard.edu/blog/generic-drugs-dont-ask-just-tell-201301075766) for Patrick J. Skerrett's much more informed and complete discussion of this issue.

Now that that's out of the way, what I really want to discuss here is ProPublica's various investigations into the relationsip between industry payments to doctors, and those doctors' tendency to perscribe brand-name drugs.  The research merged two different datasets.  The first normal Medicare Part D data, which tracks the medications perscribed by doctors.  The second is a new dataset created due to mandates in the Affordable Care Act.  Pharmaceutical and medical device companies are now required to report payments to doctors, which is released through the federal open payments database, and has been cleaned and annotated by ProPublica.  Their data can be searched by doctor using their [dollars for docs tool](https://projects.propublica.org/docdollars/)[^3] and can be purchased for stupid sums of money[^4].  These datasets were merged and analyzed in a ProPublica paper titled "Matching industry payments to Medicare prescribing patterns: an analysis."[^5].

The investigators limited their sample to the top five most common categories of physicians.  Family medicine physicians, internal medicine physicians, cardiologists, psychiatrists, and ophthamologists were kept in the sample, for a total of 150,323 physicians.  Using the medicare data, the percentage of brand-name claims out of total claims was calculated for each doctor.  These percentages were then normalized[^6] relative to the mean percentage and standard deviation within each specialty, controlling for the large differences in mean rates between the specialties.  Opthamologists, specifically, were noted as having a much higher percentage of brand-name perscrption claims in general.  Physicians with brand-name prescription rates greater than one standard deviation from the mean using this method were considered 'high brand-name prescribers".  

So what they end up with is a binary 'high brand-name prescriber' variable and a binary 'recieved any payments' variable.  They note that the percentage of doctors who recieved payments ranged between ~70 and 87 percent among the specialties.

These variables allowed the investigators to calculate risk ratios[^7].  In this case, the risk ratios are interpreted as the ratio of the probability of being a high brand-name perscriber given the doctor recieved industry payments to the probability of being a high brand-name perscriber given the doctor did not recieve any industry payments.

Doctors that receive industry payments are significantly more likely to be among the group of high-rate brand-name perscribers within their field.  

In a second section of the analysis, they demonsrate when you slice up the amount of money doctors recieved and bucket them, you see a clear, steady increase in the brand-name perscribing rate as the amount of money recieved increases.

<img src = "/img/table_6_propublic_payments.png" style="max-width:50%;min-width:50%;float:right;" alt="Table 6"/>

The investigators' analysis takes this basic framework and spins it in a number of different ways, looking at the results' sensitivity to defining their two derived variables, but they consistently get the same result.  






[^1]: Skerrett, Patrick J. “Generic Drugs: Don't Ask, Just Tell.” Harvard Health Blog, 7 Jan. 2013, www.health.harvard.edu/blog/generic-drugs-dont-ask-just-tell-201301075766.

[^2]: Jones, Ryann Grochowski, and Charles Ornstein. "Matching industry payments to Medicare prescribing patterns: an analysis." Internet Document: Mar (2016).

[^3]: https://projects.propublica.org/docdollars/

[^4]: https://www.propublica.org/datastore/dataset/dollars-for-docs

[^5]: Ornstein, Charles, et al. “Now There's Proof: Docs Who Get Company Cash Tend to Prescribe More Brand-Name Meds.” ProPublica, 9 Mar. 2019, www.propublica.org/article/doctors-who-take-company-cash-tend-to-prescribe-more-brand-name-drugs.

[^6]: https://en.wikipedia.org/wiki/Standard_score#Calculation

[^7]: https://en.wikipedia.org/wiki/Relative_risk#Inference