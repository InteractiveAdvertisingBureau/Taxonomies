# Table of Contents

- [Ad Product 2.0 Implementation Guidance](https://github.com/katieshell/Taxonomies/blob/main/implementation.md#implementation-guidance)
- [Migrating from Content 1.0](https://github.com/katieshell/Taxonomies/blob/main/implementation.md#migrating-from-content-taxonomy-10)
- [Implementation Guidance for Content 1.0 → Content 2.0](https://github.com/katieshell/Taxonomies/blob/main/implementation.md#implementation-guidance-for-content-1--content-2-mapping)

# Implementation Guidance


## Ad Product Taxonomy 2.0


### Value Proposition

**For publishers and SSPs:** Support opens a number of benefits and protections not available with previous taxonomies by being able to more easily identify, segment, and block incoming ads that may not be suitable for your content. 

**For Buyers:** Demand partners can widen their supply pool with new opportunities. More granularity also better opens the door for supply/demand collaboration in finding ads for products that better fits the content they’re running alongside. 


### How to use Ad Product Taxonomy 2.0

The Ad Product Taxonomy establishes a standardized nomenclature for describing the product or service being advertised within a creative unit. It aims to provide publishers with stronger signals to, 1) control the types of ads that are delivered via automated channels and, 2) measure the performance of those ads against internal KPIs.

It is primarily used by publishers and SSPs when blocking categories of advertisements. That said, as with all Programmatic advertising, there is so much open to interpretation that really the `adomain` attribute in OpenRTB is the ultimate thing sellers need to use to evaluate advertisers, as these categories are just a shorthand to help weed out obviously unwanted ads.


### Upgrading to Ad Product Taxonomy 2.0


#### Previously Enumerated Items

Many rows in Content Taxonomy 1.0 have been aggregated in Ad Product Taxonomy 2.0. Where additional fidelity is necessary, please create a GitHub Issue in this repository for the Taxonomy and Mapping Working Group to review. 


#### New Rows

Vague or general classifications in Content Taxonomy 1.0 have been given more specificity. For example, Music in Content Taxonomy 1.0 could be Music and Video Streaming Services, Concerts, or Musical Instruments and Record Stores. High-level mappings have been provided, but implementers are encouraged to pay close attention when doing the initial upgrade. 


#### Mappings

A mapping between Content Taxonomy 1.0 and Ad Product Taxonomy 2.0 has been produced by the Taxonomy and Mapping Working Group. While that group of experts have made best efforts to find the best possible fit, some rows do not map cleanly. All mappings should be closely reviewed by implementers prior to beginning development.  


### Ad Suitability 


#### Sensitive Categories

Some categories of advertisements are more sensitive than others. Publishers should decide which categories they deem are sensitive enough to trigger a manual creative review.

Items to keep top of mind could include



* Potentially divisive topics like Politics, Religion, and Debated Sensitive Social Issues. 
* Appropriateness of ads related to dating, dieting and weight loss, media, sexual health, and other topics where sensitivities could arise. 

Always consider questions around content adjacency and what kinds of advertisements your company feels are appropriate for your inventory. 


#### Ad Safety Risk

Ads that pose a major risk to brand safety. It is expected that this flag will be added during the creative review process (typically done by SSPs). It should only be used in conjunction with the product or service being advertised. For example, a shirt with graphic imagery would have a designation of both Clothing and Ad Safety Risk.  


#### Explicit Imagery 

Ads with explicit sexual imagery or messaging should always have a designation of Adult Products and Services. 


#### Regulatory Requirements

Implementers should pay very close attention to advertisements that fall into categories where there are regulatory requirements that vary across geographies. 

They can include, but are not limited to: 



* Regional differences in legality of cannabis or gambling
* Age restrictions on on ads for alcohol or dating
* Regulated categories like High Fat Sugar Salt foods 


### Best Practices


#### Advertising Applications

Advertisements for applications should always use the category of the application, not the app store where the application is found. 

Ads with mini-games within other applications will most likely fall under Casual Games Apps. If they are being viewed by the user in order to receive a bonus in the game they’re currently playing the `rwdd` attribute should be included in the OpenRTB.


### Glossary of Terms



* **Downloadable utilities** ([AdX definition](https://support.google.com/admob/answer/3150953?hl=en#zippy=%2Cdownloadable-utilities)): Software for download which is designed to enhance the functionality of an operating system or device, whether desktop or mobile. Typical examples include anti-virus software, file converters, driver updaters, system cleaners, download managers, disk defragmenters, codecs, browser toolbars, ringtones, screensavers, wallpapers, and so on.
* **Debated Sensitive Social Issues:** Topics in the zeitgeist with strongly held beliefs and little or no agreement between different factions. Refer to [GARM Brand Safety Floor + Suitability Framework](https://wfanet.org/l/library/download/urn:uuid:7d484745-41cd-4cce-a1b9-a1b4e30928ea/garm+brand+safety+floor+suitability+framework+23+sept.pdf) for additional guidance. 
* **Ad Safety Risk:** Advertisements containing offensive, illegal, or otherwise inappropriate imagery or text. Refer to [GARM Brand Safety Floor + Suitability Framework](https://wfanet.org/l/library/download/urn:uuid:7d484745-41cd-4cce-a1b9-a1b4e30928ea/garm+brand+safety+floor+suitability+framework+23+sept.pdf) for additional guidance. 
* **Non-Fiat Currency:** Currency not issued by a government or backed by an appropriate regulatory authority. All Cryptocurrency and NFTs fall into this category.





# Migrating from Content Taxonomy 1.0

## Summary

The industry has acknowledged that it is time to stop using Content Taxonomy 1.0, which has been deprecated since July, 2020. Simply put, there is no reason to continue using Content Taxonomy 1.0, it’s not fit for purpose for any of its current use cases.

The IAB Tech Lab’s Taxonomy and Mapping Working Group, a compilation of 112 companies across the programmatic community with expertise in taxonomies and their use in the ad tech ecosystem, has designed a suite of taxonomies for digital advertising ecosystem use cases. More recently, the group has provided mappings to help the industry transition to more suitable taxonomies for their purposes. The three main implementation use cases for this guide are:

- **Publishers** who want to describe content’s “aboutness” should upgrade to one of the more fine-grained Content Taxonomies: 2.0, 3.0, or 3.1. The working group has mapped Content Taxonomy 1.0 to the next version, Content Taxonomy 2.0 as thoughtfully as possible to ensure an upgrade path.
- **Advertisers** that are looking to categorize ads should move to Ad Product Taxonomy 2.0 which was created for the purpose of describing the product categorization of an advertisement.
- As **DSPs** move their ad library categorization from Content 1.0 to Ad Product 2.0, Publishers sending their bcats may need to know what the corresponding values are from the legacy taxonomy. To the extent possible, the working group has also mapped [Ad Product 2.0 back to Content Taxonomy 1.0.](https://github.com/katieshell/Taxonomies/blob/main/Taxonomy%20Mappings/Ad%20Product%202.0%20to%20Content%201.0.tsv)

## Content Taxonomy 1.0 to Ad Product 2.0

The mapping between Content Taxonomy 1.0 and Ad Product 2.0 helps advertisers clearly label the product categorization of their ads and publishers determine if that product is suitable for their audience. This taxonomy mapping allows partners using Content Taxonomy 1.0 to translate their existing taxonomy into a Taxonomy specifically designed to describe the product or service being advertised. The predominant use case for this upgrade is to support publisher ad blocking. Publishers have product categories that they feel aren’t appropriate to show to their audience. These could be legal requirements, like not showing alcohol to certain age groups, regulations around High Fat Sugar Salt (HFSS) products, or simply business rules, like a sports website not wanting gambling advertising on their inventory.

The mapping aims to provide a clear path for moving away from Content Taxonomy 1.0 by minimizing friction in the upgrade process. The mapping allows partners that are still using Content 1.0 to interface with Ad Product 2.0 which was created with the express purpose of categorizing the products of advertisements whereas the Content Taxonomy was created to describe the “aboutness” of content.

## Ad Product Taxonomy 2.0 to Content Taxonomy 1.0

The Ad Product Taxonomy has 191 more rows than Content Taxonomy 1.0. To be as thorough as possible and ensure that integration partners have everything that they need to move away from Content Taxonomy 1.0, the Taxonomy and Mapping working group has done a reverse mapping from Ad Product 2.0 to Content 1.0. There are far more categories of potential products to be sold in ads than there are to describe content on webpage, apps, etc. Because of this, many categories from Ad Product did not have a direct translation to the Content Taxonomy.

Ad Product Taxonomy 2.0 will give DSPs a much easier time categorizing their ads because the categories are more fit for the specific use case.

## Commonly Blocked Categories

As stated, honoring publisher blocked categories is an important feature better expressed in Ad Product 2.0. Since there is never a truly 1 to 1 relationship, the Taxonomy and Mapping Working Group sourced commonly blocked advertiser categories in Ad Product Taxonomy 2.0 to their respective values as currently sent using Content Taxonomy 1.0.

As its a critical feature, we have more detailed mapping of commonly blocked categories below:

| **Special Mappings** | **Content 1.0 Unique IDs** | **Content 1.0 Categories** | **Ad Product 2.0 Unique IDs** | **Ad Product 2.0 Categories** |
| --- | --- | --- | --- | --- |
| Alcohol | IAB8-5,IAB8-18 | Cocktails/Beer, Wine | 1002 | Alcohol |
| --- | --- | --- | --- | --- |
| Baked Goods | IAB8-8 | Desserts & Baking | 1156, 1231 | Frozen Baked Goods, Refrigerated Baked Goods |
| --- | --- | --- | --- | --- |
| Baking Ingredients | IAB8-8 | Desserts & Baking | 1168 | Baking |
| --- | --- | --- | --- | --- |
| Black Magic, Astrology & Esoteric | IAB9-20,IAB15-1 | Magic & Illusion, Astrology | 1487, 1488 | Religion and Spirituality, Astrology |
| --- | --- | --- | --- | --- |
| Cannabis/Marijuana | IAB7-5 | Alternative Medicine | 1049 | Cannabis |
| --- | --- | --- | --- | --- |
| Cosmetic Procedures & Body Modifications | IAB18-2 | Body Art | 1383 | Cosmetic Medical Services |
| --- | --- | --- | --- | --- |
| Cryptocurrency | IAB13-7 | Investing | 1448 | Non-Fiat Currency |
| --- | --- | --- | --- | --- |
| Dating | IAB14-1 | Dating | 1259 | Dating |
| --- | --- | --- | --- | --- |
| Desserts | IAB8-8 | Desserts & Baking | 1158, 1234 | Frozen Desserts, Refrigerated Desserts |
| --- | --- | --- | --- | --- |
| Downloadable Utilities | IAB9-30,IAB26-1,IAB26-2,IAB26-3,IAB26-4 | Video & Computer Games, Illegal Content, Illegal Content, Warez, Spyware/Malware, Copyright Infringement | 1028 | Computer Software |
| --- | --- | --- | --- | --- |
| Drugs & Supplements | IAB7-41,IAB7-43,IAB7-27,IAB7-22,IAB7-20,IAB7-3,IAB7-38,IAB7-6 | Smoking Cessation, Thyroid Disease, IBS/Crohn's Disease, GERD/Acid Reflux, Diabetes, AIDS/HIV, Senior Health, Arthritis | 1473 | Pharmaceuticals |
| --- | --- | --- | --- | --- |
| Fast Food | IAB8-9 | Dining Out | 1358 | Fast Food |
| --- | --- | --- | --- | --- |
| Gambling & Betting | IAB9-7 | Card Games | 1361 | Gambling |
| --- | --- | --- | --- | --- |
| Guns & Firearms | IAB17-18 | Hunting/Shooting | 1576 | Weapons and Ammunition |
| --- | --- | --- | --- | --- |
| Health Ads | IAB7 | Health & Fitness | 1378 | Health and Medical Services |
| --- | --- | --- | --- | --- |
| Hemp Based CBD | IAB7-5,IAB7-25,IAB7-26 | Alternative Medicine, Herbs for Health, Holistic Health | 1049 | Cannabis |
| --- | --- | --- | --- | --- |
| Hunting & Shooting | IAB17-18 | Hunting/Shooting | 1576 | Weapons and Ammunition |
| --- | --- | --- | --- | --- |
| Political (Elections) | IAB11-4 | Politics | 1474 | Politics |
| --- | --- | --- | --- | --- |
| Political Issues (Non-Election) | IAB11-4 | Politics | 1474 | Politics |
| --- | --- | --- | --- | --- |
| Politics | IAB11-4 | Politics | 1474 | Politics |
| --- | --- | --- | --- | --- |
| Prescription Drugs | IAB7 | Health & Fitness | 1473 | Pharmaceuticals |
| --- | --- | --- | --- | --- |
| Religion | IAB23 | Religion & Spirituality | 1487 | Religion and Spirituality |
| --- | --- | --- | --- | --- |
| Sexual & Reproductive Health | IAB7-30,IAB7-31,IAB7-39 | Infertility, Men's Health, Sexuality | 1519 | Sexual Health |
| --- | --- | --- | --- | --- |
| Significant Skin Exposure: | IAB25-3,IAB25-4 | Pornography, Profane Content | 1001 | Adult Products and Services |
| --- | --- | --- | --- | --- |
| Software | IAB3-4,IAB19-3,IAB19-16 | Business Software, Antivirus Software, Graphics Software | 1028 | Computer Software |
| --- | --- | --- | --- | --- |
| Tobacco/ Smoking Products | IAB9-9 | Cigars | 1544 | Tobacco |
| --- | --- | --- | --- | --- |
| Video Games (Casual & Online): | IAB9-30,IAB9-25 | Video & Computer Games, Roleplaying Games | 1120 | Video Games |
| --- | --- | --- | --- | --- |
| Weight Loss: | IAB7-44 | Weight Loss | 1291 | Dieting and Weightloss |
| --- | --- | --- | --- | --- |




# Implementation Guidance for Content 1 → Content 2 Mapping

## Summary

The industry has acknowledged that it is time to stop using Content Taxonomy 1.0, which has been deprecated since July, 2020. With different trading partners upgrading at different times, multiple versions of the Content Taxonomy are simultaneously in use, creating a situation that is difficult to manage and operationalize. The IAB Tech Lab’s Taxonomy and Mapping Working Group, a compilation of 112 companies across the programmatic community with expertise in taxonomies and their use in the ad tech ecosystem, has mapped Content Taxonomy 1.0 to the next version, Content Taxonomy 2.0 as thoughtfully as possible to ensure an upgrade path.

IAB Tech Lab’s Content Taxonomies are hierarchical, subsumption taxonomies. This means that the taxonomies are arranged in a tree-like structure, similar to a family tree, where:

1. Parent categories have child categories; and,
2. Child categories represent a specific sub-area of, or “a child of,” the parent category. For example, “Television” is a sub-area, or “a child of,” “Arts & Entertainment.”

## General Guidance for This Mapping

These guidelines are intended for a general audience in the ad tech space. We have endeavored to convey a high-level understanding of the mapping that will be clear to those without formal training or background in taxonomy, such as campaign designers, sellers, and software developers, while also including more fine-grained details for those with a formal background, such as information architects, data scientists and taxonomists. It is our intent that these guidelines be a useful starting point for any project to update from the v1 to the v2 of the Content Taxonomy, understanding that each project may require differences in the mapping than is presented here. We leave it to our audience to use these guidelines to update a project as is best for it.

When applying this mapping to your own implementation, keep in mind that both Content 1.0 and Content 2.0 are released taxonomies that are in production. Neither taxonomy can be changed, though customization for your implementation is an option.

No mapping between two taxonomies is ever perfect. Differences between taxonomies reflect changes in culture, society, business, economics, products and interactions while at the same time reflecting the state of the industry, use cases, and needs at the particular points in time that each taxonomy was created. Where no perfect mapping exists, the working group relied on the parent group of the previous taxonomy to suggest the most appropriate mapping.

**Implementers will have to review each piece of content currently labeled any of the below Tier 1 categories from Content 1 and map them to the most appropriate ID from Content 2. To help this process, we have included a bulleted list with values from Content 2 that may be applicable to the Content 1 ID.**

## Specific Guidance for This Mapping

### Rows with One to Many Mapping

In this mapping, the majority of rows have a 1:1 mapping, but there are a small number of cases, outlined below, that could have a many to one mapping. All mappings should be closely reviewed by implementers prior to beginning development.

There is no direct one to one mapping for these Tier 1 values between Content 1 and Content 2. The Taxonomy and Mapping Working Group has mapped each of the below categories from Content 1 to a related category in Content 2. Implementers wishing to upgrade from Content 1 to Content 2 will have to choose the most appropriate value from Content 2 from the lists below. The brackets { } are for unique category ID’s from Content Taxonomy 1.0. (The ID’s listed below are the associated values in Content 2) The final column in the mapping indicates which rows have an imperfect mapping. The type of imperfect mapping is also written.

**Arts and Entertainment {Content 1 ID = IAB1}**:

- Entertainment Content (1014)
- Fine Art (201)
- Pop Culture (432)
- Entertainment Industry (93)
- Music and Audio (338)
- Movies (324)
- Television (640)
- Video Gaming (680)

**Environmental Safety {Content 1 ID = IAB10-3}**:

- Home and Garden (274)
- Environmental Services Industry (94)
- Environment (467)

**Engines {Content 1 ID = IAB22-4}**:

- Shopping (473)
- Search Engine/Listings (1006)
- Listings/Classifieds/Product Listings/Search Results (1019)

**Comparison {Content 1 ID = IAB22-3}**:

- Shopping (473)
- Listings/Classifieds/Product Listings/Search Results (1019)

**Shopping {Content 1 ID = IAB22}**:

- Shopping (473)
- Search Engine/ Listings (1006)
- Listings/Classifieds/Product Listings/Search Results (1019)

### Rows Without Semantically Equivalent Mappings

**Radio {Content 1 ID = IAB9-24}**

In Content 2.0, Radio could be referring to two different things. It could be used to describe content about the radio OR it could be used to say that the ad will play on a radio station.

In Content 1.0, Radio {IAB9-24} is a Tier 2 category with Hobbies & Interests as a Tier 1 parent. In Content 2.0, there is no Radio category. Because of this, we mapped the Content 1 category Radio {IAB9-24} to Hobbies & Interests (239) in Content 2 since this Tier 1 category matches the parent category in Content 1.

If you are using Radio to tell your buyside partners that this ad will play on a radio station, you would need to do this using OpenRTB. In OpenRTB, this would be signaled in _Object: Content_ with the \`context\` attribute. After being signaled in OpenRTB, the implementer would use the \`genre\` attribute for the type of radio station.

**Jewelry {Content 1 ID = IAB18-4} & Accessories {Content 1 ID = IAB18-6}**

Content 2.0 does not include as many general categories as Content 1.0 so the Jewelry and Accessories categories from Content 1.0 are affected. Jewelry and Accessories are Tier 2 categories under Style & Fashion in Content Taxonomy 1.0. In Content 2.0, Accessories (561, 580) and Jewelry (565, 581) are broken up by Mens & Womens. The Working Group decided that since women’s fashion items are more frequently seen in the bid stream, we would map Jewelry from Content 1 to Women’s Jewelry and Watches (565) and Accessories from Content 1 to Women’s Accessories (561). These Content 2.0 categories should be checked by implementers to ensure that their inventory is not being labeled incorrectly.

### Mapping to Parent Category

**Immigration {Content 1 ID = IAB11-1}** - In Content Taxonomy 1, Immigration is a Tier 2 category with the parent category News and Politics. Since there was no related category, we mapped to News and Politics (379) in Content Taxonomy 2, a Tier 1 category.

**Commentary {Content 1 ID = IAB11-5}** - In Content Taxonomy 1, Commentary is a Tier 2 category with the parent category News and Politics. Since there was no related category, we mapped to News and Politics (379) in Content Taxonomy 2, a Tier 1 category.

**Nursing {Content 1 ID = IAB4-7}** - In Content Taxonomy 1, Nursing is a Tier 2 category with the parent category Careers. Since there was no analogous category, we mapped to Careers (123) in Content Taxonomy 2, a Tier 1 category.

## Unmapped Categories

Below are categories from Content 1 that do not have a related category in Content 2.0. Note that brand safety and suitability categories from Content Taxonomy 1.0 do **not** have support in Content Taxonomy 2.0 and are, therefore, unmapped. They do have support in Content Taxonomy 2.2. It is strongly recommended to use children of “Sensitive Topics” from Content Taxonomy 2.2 to fill known Brand Safety and Suitability gaps introduced by Content Taxonomy 2.0. These categories are indicated with an asterisk below and the associated Content Taxonomy 2.2 category is provided in parentheses as category id, category name. If you use these suggested v2.2 mappings, designate your entire upgrade as an upgrade to Content Taxonomy 2.2.

**IAB24 Uncategorized**

**IAB25 Non-Standard Content**

**IAB25-1 Unmoderated UGC**

**IAB25-2 Extreme Graphic/Explicit Violence**\* (v2.2 id= I4GWI6, v2.2 category name = “Death, Injury, or Military Conflict”)

**IAB25-3 Pornography**\* (v2.2 id = Rm3SiT, v2.2 category name = “Obscenity and Profanity”)

**IAB25-4 Profane Content**\* (v2.2 category id = j9PaO9, v2.2 category name = “Obscenity and Profanity”)

**IAB25-5 Hate Content**\* (v2.2 category id = HxqYV1, v2.2 category name = “Hate speech & acts of aggression”)

**IAB25-6 Under Construction**

**IAB25-7 Incentivized**

**IAB26 Illegal Content**\* (v2.2 category id = xtODT3, v2.2 category name = “Crime & Harmful acts to individuals and Society and Human Rights Violations”)

**IAB26-1 Illegal Content**\* (v2.2 category id = xtODT3, v2.2 category name = “Crime & Harmful acts to individuals and Society and Human Rights Violations”)

**IAB26-2 Warez**\* (v2.2 category id = 6i4dB6, v2.2 category name = “Spam or Harmful Content”)

**IAB26-3 Spyware/Malware**\* (v2.2 category id = mm3UXx, v2.2 category name = “Online piracy”)

**IAB26-4 Copyright Infringement**\* (v2.2 category id = mm3UXx, v2.2 category name = “Online piracy”)
