# Table of Contents

- [Ad Product 2.0 Implementation Guidance](https://github.com/katieshell/Taxonomies/blob/main/implementation.md#implementation-guidance)
- [Migrating from Content 1.0](https://github.com/katieshell/Taxonomies/blob/main/implementation.md#migrating-from-content-taxonomy-10)
- [Implementation Guidance for Content 1.0 → Content 2.0](https://github.com/katieshell/Taxonomies/blob/main/implementation.md#implementation-guidance-for-content-1--content-2-mapping)
- [Content Taxonomy 3.0 Implementation Guidance]

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
| Baked Goods | IAB8-8 | Desserts & Baking | 1156, 1231 | Frozen Baked Goods, Refrigerated Baked Goods |
| Baking Ingredients | IAB8-8 | Desserts & Baking | 1168 | Baking |
| Black Magic, Astrology & Esoteric | IAB9-20,IAB15-1 | Magic & Illusion, Astrology | 1487, 1488 | Religion and Spirituality, Astrology |
| Cannabis/Marijuana | IAB7-5 | Alternative Medicine | 1049 | Cannabis |
| Cosmetic Procedures & Body Modifications | IAB18-2 | Body Art | 1383 | Cosmetic Medical Services |
| Cryptocurrency | IAB13-7 | Investing | 1448 | Non-Fiat Currency |
| Dating | IAB14-1 | Dating | 1259 | Dating |
| Desserts | IAB8-8 | Desserts & Baking | 1158, 1234 | Frozen Desserts, Refrigerated Desserts |
| Downloadable Utilities | IAB9-30,IAB26-1,IAB26-2,IAB26-3,IAB26-4 | Video & Computer Games, Illegal Content, Illegal Content, Warez, Spyware/Malware, Copyright Infringement | 1028 | Computer Software |
| Drugs & Supplements | IAB7-41,IAB7-43,IAB7-27,IAB7-22,IAB7-20,IAB7-3,IAB7-38,IAB7-6 | Smoking Cessation, Thyroid Disease, IBS/Crohn's Disease, GERD/Acid Reflux, Diabetes, AIDS/HIV, Senior Health, Arthritis | 1473 | Pharmaceuticals |
| Fast Food | IAB8-9 | Dining Out | 1358 | Fast Food |
| Gambling & Betting | IAB9-7 | Card Games | 1361 | Gambling |
| Guns & Firearms | IAB17-18 | Hunting/Shooting | 1576 | Weapons and Ammunition |
| Health Ads | IAB7 | Health & Fitness | 1378 | Health and Medical Services |
| Hemp Based CBD | IAB7-5,IAB7-25,IAB7-26 | Alternative Medicine, Herbs for Health, Holistic Health | 1049 | Cannabis |
| Hunting & Shooting | IAB17-18 | Hunting/Shooting | 1576 | Weapons and Ammunition |
| Political (Elections) | IAB11-4 | Politics | 1474 | Politics |
| Political Issues (Non-Election) | IAB11-4 | Politics | 1474 | Politics |
| Politics | IAB11-4 | Politics | 1474 | Politics |
| Prescription Drugs | IAB7 | Health & Fitness | 1473 | Pharmaceuticals |
| Religion | IAB23 | Religion & Spirituality | 1487 | Religion and Spirituality |
| Sexual & Reproductive Health | IAB7-30,IAB7-31,IAB7-39 | Infertility, Men's Health, Sexuality | 1519 | Sexual Health |
| Significant Skin Exposure: | IAB25-3,IAB25-4 | Pornography, Profane Content | 1001 | Adult Products and Services |
| Software | IAB3-4,IAB19-3,IAB19-16 | Business Software, Antivirus Software, Graphics Software | 1028 | Computer Software |
| Tobacco/ Smoking Products | IAB9-9 | Cigars | 1544 | Tobacco |
| Video Games (Casual & Online): | IAB9-30,IAB9-25 | Video & Computer Games, Roleplaying Games | 1120 | Video Games |
| Weight Loss: | IAB7-44 | Weight Loss | 1291 | Dieting and Weightloss |



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


# Content Taxonomy 3.0 Implementation Guidance

## Content Taxonomy Overview

The IAB Tech Lab Content Taxonomy provides a “common language” that all parties—publishers, Server- Side Providers (SSPs), Demand-Side Providers (DSPs), verification vendors, and advertisers—can use and understand when describing the content of a page, app, or other user environment. The content taxonomy is useful in two main use cases— addressability (or contextual targeting) and brand safety/suitability (introduced in 2.2).

In addition to the Content Taxonomy, the Taxonomy Working Group has also defined an “Ad Product Taxonomy” and an “Audience Taxonomy” (to describe the product being advertised and an audience segment, respectively). The relevant taxonomies should be used based on the use case.

The 3.0 version of the taxonomy does not introduce new concepts, but did result in breaking changes (not backwards compatible due to removal of parent categories) when updating to better support video, news, podcasts, games and app categories. It also included updates to the “vectors”.

## Using the Content Taxonomy

The 2.x & 3.x content taxonomy includes two parts – a set of categories that describe the topic context or “aboutness”, and an additional set of orthogonal content attributes / “vectors” such as content language, format, language, source, media type, etc. These are all associated with IDs that are used when communicating information about a piece of content.

The IDs within the Taxonomy specs should be used when tagging content. The IDs are alphanumeric strings (though a large number are currently sequential numbers to maintain backwards compatibility) associated with each category or orthogonal attribute. The implementations involved may be different depending on the application—OpenRTB (real-time bidding) or digital video ad serving template (VAST) or proprietary application programming interfaces (APIs)—but the most common usage is to associate a piece of content with an array of IDs.

With OpenRTB / AdCOM (Advertising Common Object Model), the “cat” attribute should be used to transmit a list of categories associated with the content and the “cattax” attribute should be set to 2 (for Content Taxonomy version 2.x and higher). These attributes are available on Ad, Site, App, Publisher, Producer, and Content objects.


_Note 1 : The SCD (“Special Category Data”) extension in the Taxonomy is an additional utility aimed at minimizing the risk that content categorization signals could be used to generate sensitive data points about things like race, politics, religion or other personal characteristics that could result in discrimination. While the Content Taxonomy itself doesn’t constitute sensitive data – it simply categorizes page content, and does not on its own reveal information about a user – there are few technical controls preventing taxonomy nodes being associated with individual IDs to build behavioral profiles over time based on content preferences. Content Taxonomy 2.1 helps to limit this possibility by introducing a “sensitive data” flag to taxonomy nodes that could be used to generate this data, and provides a clear signal to supply chain participants regarding the privacy implications of storing it._


### Descriptions of the “Vectors”

Given the large number of items in the taxonomy, we are not providing descriptions for every item. However, we believe it is important to provide some basic guidance around the “Vectors” in the taxonomy, as part of this implementation guide.


|Category |Description|
|-----------|-----------|
|Content Environment |Describes the surrounding platform (distinct from device)|
|Email Content| delivered as email|
|Forum/Community Content| appearing in a forum / community tool/app/page.|
|Marketplace/eCommerce Content| appearing in a marketplace / ecommerce property.|
|Search Engine/Listings Content| appearing in a search engine listing.|
|Social Content| appearing in social media app/page|
|Utility/Online Tool Content| appearing in a utility/tool|
|Voice Activated Channels Content| appearing in voice activated channels (like Alexa, Google home etc)|
|General Content| delivered via the web,Includes free and paid content, and does not belong in any of the other environments above.|
|Content Purpose| Describes the purpose of the content (The reason the content was created)|
|Conversational Purpose| is to have an interactive exchange of questions, answers, back and forth. Examples - Chat/IM/Comments etc.|
|Entertainment Content| built for entertainment purposes.|
|Informational Content| that has the purpose of providing information at length, in depth or that provides background information|
|Informational -> Academic/Research Content| Content that has the purpose of supporting specific fields of study and investigation|
|Informational -> Educational Content Content| that has the purpose of supporting structured or formal instruction|
|Informational -> Instructional Content| Content that has the purpose of describing how to do things or how things work|
|Informational → News Content| that has the purpose of providing previously unknown information (for the majority of the audience)|
|Informational → News -> Opinions and Op Eds| Content that presents views or judgements about current events, world affairs or other topics as a part of a news publication.|
|Informational -> Review Content| that has the purpose of presenting a critical assessment of something, such as of a movie, book, restaurant, product, a company, practitioner or consumer experience|
|Commerce Content| that supports or has the purpose of facilitating buying and selling goods or services|
|Content Source| Describes the origin of the content and the authority of its producer.|
|Professionally Produced Content| produced by professionals, with editorial oversight.|
|User Generated Content| produced by writers/producers without editorial oversight.|
|Aggregated/Curated Content| aggregated from third party sources.|
|Content Form Factor| Describes the data format of the content, or the nature of how the content will be experienced.|
|Audio Content| that is based entirely on sound that is recorded, transmitted or reproduced|
|Audio -> Podcast| “A digital audio file made available on the Internet for downloading to a computer or mobile device, typically available as a series, new installments of which can be received by subscribers automatically.”|
|Audio -> Radio| Audio content that is transmitted by radio waves for broadcast to a large audience.|
|Audio -> Event| Audio content that covers important social occasions, activities, competitions, including sports competitions, or other significant happenings that are of interest to the general public, such as pageants, awards presentations or other major occurrences, occasions or activities that are news-worthy, notable or of some importance|
|Images/Galleries Content| that presents pictures and visual representations presented individually or as a group|
|Mixed Content| that combines multiple form factors where no single form factor is dominant|
|Textual Content| made up of text, i.e., written or printed words|
|Video Content| made up of moving visual images|
|Video -> Show| A show is the main body of any content produced for broadcast via over-the-air, satellite, cable, or internet, and does not include breaking news, advertisements, or trailers that are typically placed between shows|
|Video -> Show -> Episodic show| Two or more shows in a sequential series that together make up a single body of work.|
|Video -> Event| Broadcasts and content that cover certain important social occasions, activities, competitions, including sports competitions, or other significant happenings that are of interest to the general public , such as pageants, sports matches, breaking news, awards presentations or other major occurrences, occasions or activities that are news-worthy or of some importance.|
|Video -> Clip| A segment of a longer piece of video content, such as a movie, show or event coverage. television program / highlights.|
|Video -> Movie| A motion picture, created with producer control and distributed on a television network, streaming service, inmovie theaters or via other distribution channels|
|Game| A game on any delivery platform (app, console, etc).|
|VR/AR Content| that is virtual or augmented reality|
|Brand Suitability and Risk| Defined in the GARM / 4As/APB specs|
|Floor| Defined in the GARM / 4As/APB specs|
|High Risk| Defined in the GARM / 4As/APB specs|
|Medium Risk| Defined in the GARM / 4As/APB specs|
|Low Risk| Defined in the GARM / 4As/APB specs|

## Brand Safety: Floor & Suitability Support in 2.2+

The Brand Safety Floor & Suitability concepts introduced in the 2.2 version of the Content Taxonomy are based on the Brand Safety & Suitability Framework released in September 2020 by the Global Alliance for Responsible Media (GARM) in collaboration with the American Association of Advertising Agencies’ (4As) Advertiser Protection Bureau (APB). For the purposes of the Content Taxonomy v2.2, the descriptions for each category at each risk level, including the Floor, are described in the framework. The goal of including these categories are twofold. First, to provide a mechanism to mark content that might not be suitable for certain brands, but equally important, to allow content that might otherwise have been blanket marked as unsafe to be monetized by allowing brands with the right risk tolerance to buy such inventory.

The 11 Brand Safety categories identified in the framework are introduced in v2.2 of the Content Taxonomy as topic categories under the parent category “Sensitive Topics” (id “v9i3On” in the Content Taxonomy 2.2 spreadsheet). The 11 categories are:

1. Adult & Explicit Sexual Content
2. Arms & Ammunition
3. Crime & Harmful acts to individuals and Society and Human Right Violations
4. Death Injury, or Military Conflict
5. Online piracy
6. Hate speech & acts of aggression
7. Obscenity and Profanity
8. Illegal Drugs/Tobacco/eCigarettes/ Vaping/Alcohol
9. Spam or Harmful Content
10. Terrorism
11. Sensitive Social Issues

The risk levels in the Framework that identify the levels of suitability are treated as additional attributes of the content. They are encoded in an orthogonal vector accordingly, allowing “risk” to be associated with a “topic” dynamically. The levels are:

1. Floor
2. High Risk
3. Medium Risk
4. Low Risk

_Note 1: at the time of release (October 2020), the only topics in the Content Taxonomy that are expected to carry risk associations are the 11 Brand Safety categories. The Tech Lab’s Taxonomy Working Group will work with our members as well as with GARM and IAB to determine whether the risk associations can be applied to other categories in the future._

_Note 2: the orthogonal attributes supported by the taxonomy, like content type and source, could be used as additional signals since they have implications to suitability (for example news)._


## Content Taxonomy Usage Guidance for Buyers

**_Brand safety:_**
Buyers should familiarize themselves with the GARM/4A’s APB Brand Safety & Suitability Framework and the Tech Lab Content Taxonomy. They should also understand the risk/tolerance levels they are comfortable with by looking at examples of the various suitability examples. They should then work with their DSPs and ad verification vendors to ensure that their goals are met by specifying the risk tolerance goals using the Content Taxonomy.

**_Addressability/Targeting:_**
With the increased awareness of user privacy concerns, contextual targeting is becoming more important. The Content Taxonomy enables buyers to use a consistent language across all publishers and platforms. Buyers should also map any specific areas of interest to the Content Taxonomy categories so that the most relevant content can be targeted for their campaigns.

## Implementation Guidance for Ad Verification Vendors

Ad verification vendors are likely to be the main implementers of the brand safety floor and suitability. As such, the recommendations provided here would also apply to any other audience implementing brand safety checks.

Recommendations:

- Ad verification vendors should apply any relevant Content Taxonomy categories to a given piece of content, and/or any of the 11 brand safety categories
- Ad Verification vendors should apply a risk level whenever any of the 11 core brand safety category labels are applied to a piece of content.
- It is possible to have multiple brand safety category labels (and appropriate risk levels with each brand safety category label) associated with a given piece of content.
- As of v2.2, ad verification vendors are not required to apply risk levels to topic categories other than the 11 core Brand Safety categories in the Content Taxonomy.
- As indicated above, the descriptions for the categories at various risk levels are from the GARM/4As APB Framework.
- In addition to brand safety, ad verification vendors might also provide more information about the topic context using the other categories on the content taxonomy.


Since the integration between DSPs and verification vendors is done via proprietary APIs, OpenRTB or other standards are not relevant here, and the guidance provided below should be considered pseudo-code rather than actual samples.

The proprietary API would at a minimum have the following:

1. **Request** : pass in the URL to the content being analyzed.
2. **Response** : return an array of objects, each of which represent a category & suitability for that category. When suitability info is not available, such as when topic categories other than the 11 core brand safety categories are applied, the suitability field would be null.

For example, to describe a piece of content that belongs to 3 content categories (“Arms & Ammunition”, “Hate speech & acts of aggression”, and “Casual games”). Of these, the vendor has determined that the content is at “high risk” for “Arms & Ammunition” and “low risk” for “Hate speech & acts of aggression”, the response could look like the following:

_{
...
“catswithsuitability”:
[
{
“category” : “avbNf2”,
“suitability” : “bsr002”
},
{
“category” : “HxqYV1”,
“suitability” : “bsr004”
},
{
“category” : “693”,
“suitability” : null
},
]
...
}_


## Implementation Guidance for DSPs

**_Brand safety:_**
DSPs would likely need to implement the following set of capabilities to support brand safety checks for buyers.

1. A user interface to allow buyers to define their acceptable “risk tolerance” levels (high/med/low) for the 11 core brand safety categories as they set up their campaigns.
2. A workflow where they accept the content URL from the publisher/SSP and pass it along to an ad verification vendor.
3. Use the response from the ad verification vendor (as described above) to decide which pieces of content match the buyer’s brand safety risk tolerance for that brand.

**_Addressability/Targeting:_**
In order to allow buyers to target campaigns based on interest, DSPs should make the categories from the Content Taxonomy available in their campaign creation workflows. DSPs might also have integrations with ad verification vendors to check the content and verify the categories for the content.

## Implementation Guidance for Publishers & SSPs

**_Brand safety:_**
To support brand safety and suitability, there are two key areas publishers and server-side providers (SSPs) should be aware of and implement support for:

1. Floor content
    The key guidance to publishers and SSPs is that they should strongly consider preventing the presence of content that would receive a “Floor” risk level in association with any of the 11 Brand Safety categories. Barring that, at a minimum they should consider not monetizing or allowing advertising on any such content.
2. Providing context
    When making ad requests, publishers and SSPs should tag each piece of content with the relevant content categories from the Content Taxonomy and provide those in the OpenRTB or VAST bid request (as described in section 2). It is very likely that the buy side platforms will want to perform their own analysis using ad verification vendors of the content categories, as well as the floor & suitability checks. So, Publishers/SSPs should also provide the URL of the content, so that the ad verification vendors can perform their checks.


At this time OpenRTB does not support the ability to pass suitability information per category (a general suitability level can be passed now). We are working on an OpenRTB extensions to support that capability. The extension would allow an array of objects with brand safety category and associated risk tolerance levels - similar to the sample in the Section 5.

_Note: We would like to solicit feedback during public comment on whether publishers/SSPs plan to send suitability information in ad requests, and also whether DSPs/buyers would use that signal if it comes from publishers/SSPs. At a minimum this information could be a starting point that can be verified by the buy side._

**_Addressability/Targeting:_**
Publishers and SSPs should populate ad requests in OpenRTB or VAST (or other integrations) with relevant Content Taxonomy categories for each piece of content, so that buyers can execute contextual targeting on the requests. In addition, the pageurl should be sent along so that ad verification vendors and DSPs can confirm the categorization themselves.

## Using the Content Taxonomy for News use cases

We introduced a number of changes in 3.0 to better support News use cases.

First, we updated the “Content Purpose” vector with an “Informational” category, and child nodes including “News”, “Opinion & Op-Ed”, which are relevant to news. Second, we removed the “News & Politics” aboutness category to avoid limiting news to only that tree. Finally, we are recommending that any of the aboutness categories can be used along with the News related vectors.

This means, for any piece of content, at a minimum we recommend using:

1. “Content Purpose” vectors related to news - (News, Opinion & Op-Ed)
2. Any relevant aboutness categories
3. Any other vectors (like “Content Environment”, ”Content Source”, “Content Form Factor”, etc.


## Using the Content Taxonomy for Video use cases

Similar to News, in Content Taxonomy 3.0 we have introduced some changes to better support Video genres.

1. Television and Movies are no longer parent categories whose children are the only supported genres. Now any aboutness category can be used to represent relevant genres. That said, added an “Entertainment Genres” group of categories to better support Genres in general. In addition, we have listed the most common video genres below - though other categories can be used too.
2. Television and Movies are now only intended to be used to mark content related to TV or Movies - not that they are TV shows or Movies themselves.
3. We have now introduced a set of “Content Form Factor” vector values (Video, Show, Event, Clip, Movie) that should be used for video content.

**Common Video Genre categories recommended for Video (all under the “Genres” parent):**

- Animation & Anime
- Soap Opera
- Special Interest (Indie/Art House)
- Family/Children
- Comedy
- Drama
- Factual
- Reality TV
- Science Fiction
- Action/Adventure
- Romance
- Mystery
- Documentary
- Horror
    - History
    - Lifestyle
    - Talk Show
    - Western
    - Fantasy
    - Musicals
    - Holiday
    - Nature
    - Sports Radio
    - Talk Radio
    - Public Radio
    - Biographies
    - Young Adult
    - Music Video

**“Content Form Factor” vector values:**

- Video
- Show
- Episodic Show
- Event
- Clip
- Movie


## Using the Content Taxonomy for Podcasts

1. Form factor Vector : Podcast
2. Aboutness - Any of the aboutness categories can be used, but recommendations for the most common podcast categories are listed below.
3. The list below is just the generic recommendation for the podcast categories, but if more intelligence about the podcast is available, a more accurate category should be used. **In fact, we** **recommend that more intelligence should be applied since the generic categorization** **provided by Apple or other platforms may not be sufficiently accurate.**
4. Also, as always, multiple categories can also be used if there is overlap across categories.

Refer to Podcast Mapping to Content 3.1


## 11. Using the Content Taxonomy for Games

1. Form factor Vector : Game
2. Aboutness - Any of the aboutness categories can be used, but recommendations for the most
    common game categories are listed below.
3. The list below is just the generic recommendation for the game categories, but if more
    intelligence about the game is available, a more accurate category should be used. In fact, we
    recommend that more intelligence should be applied since the generic categorization provided
    by the platforms may not be sufficiently accurate.
4. Also, as always, multiple categories can also be used if there is overlap across categories.


|Apple| Google| Playstation| Xbox| PC/Steam| IABTL Content Taxonomy Aboutness categories|
|-----|-----|-----|-----|-----|-----|
|Action| Action| Action| Action &Adventure| Action| Action-Adventure Video Games|
|Adventure| Adventure| Adventure| Action & Adventure| Adventure Action-Adventure Video Games|
| | |Adult| | | Adult Video Games|
| |Arcade| Arcade| | Arcade| Action Video Games|
|AR Games| | | | | *Use most relevant aboutness depending on game And use the VR/AR form factor in addition to the Game form factor|
|Board| Board| | | Card & Board| Puzzle Video Games|
|Card| Card| | | Card & Board| Puzzle Video Games|
|Casino| Casino| | | | Casino and Gambling Video Games|
|Casual| Casual| Casual| | Casual| Casual Games|
| |Educational| Educational| | | Educational Video Games|
|Family| | Family| Kids & Family| | Family Video Games|
| | Fighting| Fighting| Fighting & Martial Arts| Action Video Games|
| | |Fitness| | | Exercise and Fitness Video Games|
| | |Horror| | | Horror Video Games|
|Indie| | | Indie | |*Use most relevant aboutness depending on game|
|Kids| | | Kids & Family| | Family Video Games|
|Music| Music| Music/Rhythm| | |Music and Party Video Games|
| | |Party| | | Music and Party Video Games|
| | |Platform| | Platformer & Runner| Action Video Games|
|Puzzle| Puzzle| Puzzle| | Puzzle |Puzzle Video Games|
|Racing| Racing| Racing| Racing & Flying| Racing Racing Video Games|
|Role-Playing| Role-Playing| Role-Playing| Role-Playing| Role-Playing| Role-Playing Video Games|
| | |Shooter| Shooter| Shooter| Action Video Games|
|Simulation| Simulation| Simulation| | Simulation |Simulation Video Games|
|Sports| Sports| Sports| Sports| Sports| Sports Video Games|
|Strategy| Strategy| Strategy| Strategy| Strategy| Strategy Video Games|
|Trivia| Trivia| | | | Puzzle Video Games|
| | |Unique| | | N/A - Would not include|
|Word| Word| | | | Puzzle Video Games|

## Using the Content Taxonomy for App store categories

Any of the aboutness categories can be used, but the most common ones are listed below, based on current app store categories on the most popular app stores (iOS and Google Play). The list below is just the generic recommendation for the app store categories, for any given app, if more intelligence about the app is available, a more accurate category should be used. In fact, we recommend that more intelligence should be applied since the generic categorization provided by the platforms may not be sufficiently accurate. As always, multiple categories can also be used if there is overlap across categories.


|iOS App store categories| Google Play categories| IABTL Content Taxonomy Aboutness categories|
|-----|-----|-----|
|Graphics & Design| Art & Design| Design|
| |Auto & Vehicles| Automotive|
| |Beauty| Beauty|
|Books| Books & Reference| Books and Literature|
|Reference| | *Use most relevant aboutness depending on the app|
|Business| Business| Business and Finance|
| |Comics| Comics and Graphic Novels|
| |Communications| Communication|
| |Dating| Dating|
|Education| Education| Education|
|Entertainment| Entertainment|Entertainment|
| |Events| Events|
|Finance| Finance| Business and Finance|
|Food & Drink| Food & Drink| Food & Drink|
|Games| Games| Video Gaming|
|Health & Fitness| Health & Fitness| Fitness and Exercise|
| |House & Home| Home & Garden|
|Kids| | Genres -> Family/Children|
|Developer Tools| Libraries & Demo| Technology & Computing (Or other relevant aboutness categories) Also use the “Educational content” vector|
|Lifestyle| Lifestyle| Genres -> Lifestyle|
|Navigation| Maps & Navigation| Maps & Navigation|
|Medical| Medical| Medical Health|
|Music| Music & Audio| Music|
|Magazines & Newspapers| News & Magazines| *Use most relevant aboutness depending on the app Also use Entertainment and/or News vectors as relevant|
|News| |*Use most relevant aboutness depending on the app And use the News vector|
| |Parenting |Parenting|
| |Personalisation| Software and Applications|
|Photo & Video| Photography| Photo Editing Software|
|Productivity| Productivity| Productivity|
|Safari Extensions| | Productivity|
|Shopping| Shopping| Shopping|
|Social Networking| Social| Social Networking|
|Sports |Sports |Sports|
|Stickers| | *Use most relevant aboutness depending on the app|
|Utilities| Tools| Productivity|
|Travel| Travel and local| Travel|
| |Video players and editors| Software and Applications|
|Weather| Weather| Weather|


## Using the Content Taxonomy for Radio use cases

1. Form factor Vector : Radio
2. Aboutness - Any of the aboutness categories can be used, but recommendations for the most common Radio related genres are listed below.
3. The list below is just the generic recommendation for the Radio categories, but if more intelligence about the content is available, a more accurate category should be used.
4. Also, as always, multiple categories can also be used if there is overlap across categories.

**IABTL Content Taxonomy Aboutness categories**

- Sports Radio
- Talk Radio
- Public Radio
- Adult Contemporary Music
- Soft AC Music
- Urban AC Music
- Adult Album Alternative
- Alternative Music
- Children’s Music
- Classic Hits
- Classical Music
- College Radio
- Comedy (Music and Audio)
- Contemporary Hits/Pop/Top 40
- Country Music
- Dance and Electronic Music
- World/International Music
- Songwriters/Folk
    - Gospel Music
    - Hip Hop Music
    - Inspirational/New Age Music
    - Jazz
    - Oldies/Adult Standards
    - Reggae
    - Blues
    - Religious (Music and Audio)
    - R&B/Soul/Funk
    - Rock Music
    - Album-oriented Rock
    - Alternative Rock
    - Classic Rock
    - Hard Rock
    - Soft Rock
    - Soundtracks, TV and Showtunes
    - Urban Contemporary Music
    - Variety (Music and Audio)

_Note 1: For news, refer to the news section, and use the news related vectors, as well as any relevant aboutness categories - like “Business” to reflect Business News_

_Note 2: For Educational, use the “Educational Content” vector, along with any relevant aboutness categories._
