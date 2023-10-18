
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
