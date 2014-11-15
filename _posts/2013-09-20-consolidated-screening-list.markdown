---
published: true
permalink: "consolidated-screening-list.html"
layout: body
---

# ITA Consolidated Screening List

## Background

The Consolidated Screening List API consolidates nine export screening lists of the Departments of Commerce, State and the Treasury into one spreadsheet as an aide to industry in conducting electronic screens of potential parties to regulated transactions. In the event that a company, entity or person on the list appears to match a *party* potentially involved in an export transaction, additional due diligence should be conducted before proceeding. There may be a strict export prohibition, requirement for seeking a license application, evaluation of the end-use or user to ensure it does not result in an activity prohibited by any U.S. export regulations, or other restriction.

##Instruct Users How to Stay Compliant

Developers must provide the following information to their users to help them [stay compliant with exporting law](http://export.gov/ecr/index.asp).

*If a party to a user’s transaction matches the name of a party on the consolidated list, the user must check the official publication of restricted parties in the [Federal Register](http://www.gpoaccess.gov/fr/) or the official lists of restricted parties maintained on the websites of the Departments of Commerce, State and the Treasury to ensure full compliance with all of the terms and conditions of the restrictions placed on the parties on this list.  Links to these websites are found below as well as in the “Source List URL” and “Source Information URL” fields that accompany each party returned in the API.  These links connect users to the specific webpage that contain additional information about how to use each specific list.*

Test the API using the [demo search app](http://internationaltradeadministration.github.io/explorer/#/consolidated-screening-list-entries)

##Resource URL
The below URL will search across all nine screening lists. To search a subset, see sources below.

[http://api.trade.gov/consolidated_screening_list/search](http://api.trade.gov/consolidated_screening_list/search)

##Search Parameters for consolidated screening list sources

###keyword

Searches for a match within the **name**, **remarks**, and **title** fields from all nine lists.

    http://api.trade.gov/consolidated_screening_list/search?q={term}

**_Example_**

[http://api.trade.gov/consolidated_screening_list/search?q=chemical](http://api.trade.gov/consolidated_screening_list/search?q=chemical)

###sources

Searches only the lists specified by the **Source** Abbreviation.

    http://api.trade.gov/consolidated_screening_list/search?sources={csl_type}

**_Example_**

[http://api.govwizely.com/consolidated_screening_list/search?sources=ISN,SDN](http://api.govwizely.com/consolidated_screening_list/search?sources=ISN,SDN)
	
Source Abbreviations as follows:

* Denied Persons List = **DPL**
* Entity List = **EL**
* Foreign Sanctions Evaders = **FSE**
* ITAR Debarred = **DTC**
* Nonproliferation Sanctions = **ISN**
* Palestinian Legislative Council List = **PLC**
* Sectoral Sanctions Identifications List = **SSI**
* Specially Designated Nationals - **SDN**
* Unverified List = **UVL**

###countries

Searches only parties whose **country** field matches the country code based on ISO [alpha-2 country codes](http://www.iso.org/iso/home/standards/country_codes/country_names_and_code_elements.htm).  Note:  This method allows you to search for multiple countries (plural) but will only return one country (singular) per party.  

    http://api.trade.gov/consolidated_screening_list/search?countries={country code}

**_Example_**

[http://api.trade.gov/consolidated_screening_list/search?countries=JO,PS](http://api.trade.gov/consolidated_screening_list/search?countries=JO,PS)

###size + offset

The size parameter allows you to configure the maximum amount of hits to be returned. The offset parameter defines the offset from the first result you want to fetch.

**_Example_**

[http://api.trade.gov/consolidated_screening_list/search?country=PS&size=1&offset=1](http://api.trade.gov/consolidated_screening_list/search?country=PS&size=1&offset=1)

###The Nine Screening Lists, Their Sources and Specific Fields

Each list returns a unique set of fields.  Where appropriate, the Consolidated Screening List normalizes the field names, such as **address**, **start_date**, and **federal_register_notice**.

####Department of Commerce – Bureau of Industry and Security (BIS)

* [Denied Persons List](http://www.bis.doc.gov/dpl/default.shtm) -- Individuals and entities that have been denied export privileges. Any dealings with a party on this list that would violate the terms of its denial order are prohibited.

| Field	| Description |
| ------| -------------|
| address | Entity's street/PO address |
| end_date | The date on which the entity's inclusion on the list will be lifted, wavied, or will have expired | 
| federal_register_notice | The official source of information about the parties on this list | 
| name | Entity's name | 
| remarks | Additional remarks or notes regarding the company, entity, or person on the list. | 
| standard_order | Whether or not (Y/N) the [standard order](http://www.bis.doc.gov/index.php/policy-guidance/lists-of-parties-of-concern/denied-persons-list/12-policy-guidance/list-parties-of-concern/321-the-denied-persons-list-standard-order) applies to the Denied Party as defined by the Bureau of Industry and Security (BIS)|
| start_date  | The effective date for the entity to be included on the list as defined by the Federal Register Notice |
| source_list_url | Location of the original list | 
| source_information_url | Information from the Source agency about the list |


* [Entity List](http://www.bis.doc.gov/entities/default.htm) -- Parties whose presence in a transaction can trigger a license requirement supplemental to those elsewhere in the Export Administration Regulations (EAR). The list specifies the license requirements and policy that apply to each listed party.

| Field	| Description |
| ------| -------------|
| address | Entity's street/PO address |
| alt_names | Alias names used by the entity | 
| entity_number | Unique id assigned by the originating list. 
| federal_register_notice | The official source of information about the parties on this list | 
| license_requirement | The license requirement as determined by the Export Administration Regulations |
| license_policy | The policy set forth in the Export Administration Regulations regarding denial |
| name | Entity's name | 
| programs | Agency program related to the entity on the list |
| standard_order | Whether or not (Y/N) the [standard order](http://www.bis.doc.gov/index.php/policy-guidance/lists-of-parties-of-concern/denied-persons-list/12-policy-guidance/list-parties-of-concern/321-the-denied-persons-list-standard-order) applies to the Denied Party as defined by the Bureau of Industry and Security (BIS)|
| start_date  | The effective date of the entity on the list as defined by the Federal Register Notice |
| end_date | The date on which the entity’s inclusion on the list will be lifted, wavied, or will have expired | 
| source_list_url | Location of the original list | 
| source_information_url | Information from the Source agency about the list |


* [Unverified List](http://www.bis.doc.gov/enforcement/unverifiedlist/unverified_parties.html) -- End-users who BIS has been unable to verify in prior transactions. The presence of a party on this list in a transaction is a “Red Flag” that should be resolved before proceeding with the transaction.

| Field	| Description |
| ------| -------------|
| address | Entity's street/PO address |
| alt_names | Alias names used by the entity | 
| name | Entity's name | 
| source_list_url | Location of the original list | 
| source_information_url | Information from the Source agency about the list |

####Department of State – Bureau of International Security and Non-proliferation

* [Nonproliferation Sanctions](http://www.state.gov/t/isn/c15231.htm) -- Parties that have been sanctioned under various statutes. The linked webpage is updated as appropriate, but the Federal Register is the only official and complete listing of nonproliferation sanctions determinations.

| Field	| Description |
| ------| -------------|
| federal_register_notice | The official source of information about the parties on this list |
| name | Entity's name | 
| programs | Agency program related to the entity on the list |
| start_date  | The effective date of the entity on the list as defined by the Federal Register Notice |
| end_date | The date on which the entity’s inclusion on the list will be lifted, wavied, or will have expired | 
| source_list_url | Location of the original list | 
| source_information_url | Information from the Source agency about the list |

####Department of State – Directorate of Defense Trade Controls

* [ITAR Debarred List](http://www.pmddtc.state.gov/compliance/debar_intro.html) -- Entities and individuals prohibited from participating directly or indirectly in the export of defense articles, including technical data and defense services.  Pursuant to the Arms Export Control Act (AECA) and the International Traffic in Arms Regulations (ITAR), the AECA Debarred List includes persons convicted in court of violating or conspiring to violate the AECA and subject to “statutory debarment” or persons established to have violated the AECA in an administrative proceeding and subject to “administrative debarment.”

| Field	| Description |
| ------| -------------|
| alt_names | Alias names used by the entity | 
| federal_register_notice | The official source of information about the parties on this list | 
| name | Entity's name | 
| programs | Agency program related to the entity on the list |
| start_date  | The effective date of the entity on the list as defined by the Federal Register Notice |
| source_list_url | Location of the original list | 
| source_information_url | Information from the Source agency about the list |


####Department of the Treasury – Office of Foreign Assets Control (OFAC)

* [Foreign Sanctions Evaders List](http://www.treasury.gov/resource-center/sanctions/SDN-List/Pages/fse_list.aspx) -- Foreign individuals and entities determined to have violated, attempted to violate, conspired to violate, or caused a violation of U.S. sanctions on Syria or Iran, as well as foreign persons who have facilitated deceptive transactions for or on behalf of persons subject to U.S. Sanctions. Transactions by U.S. persons or within the United States involving Foreign Sanctions Evaders (FSEs) are prohibited.

* [Palestinian Legislative Council List](http://www.treasury.gov/resource-center/sanctions/Terrorism-Proliferation-Narcotics/Pages/index.aspx) -- The individuals in this list are Palestinian Legislative Council members who were elected on the party slate of a Foreign Terrorist Organization, Specially Designated Terrorist, or Specially Designated Global Terrorist. They do not, however, appear on the SDN List.  Transactions involving these individuals must be rejected.

* [Sectoral Sanctions Identifications List](http://www.treasury.gov/resource-center/sanctions/SDN-List/Pages/ssi_list.aspx) -- 
This Sectoral Sanctions Identifications List includes persons determined by OFAC to be operating in sectors of the Russian economy identified by the Secretary of the Treasury pursuant to Executive Order 13662. The prohibitions on dealings related to the persons identified on this list are described in the [Sectoral Sanctions Identifications List circular](http://www.treasury.gov/ofac/downloads/ssi/ssi.pdf).

* [Specially Designated Nationals List](http://www.treasury.gov/resource-center/sanctions/SDN-List/Pages/default.aspx) -- Parties who may be prohibited from export transactions based on OFAC’s regulations. The Export Administration Regulations (EAR) require a license for exports or re-exports to any party in any entry on this list that contains any of the suffixes "SDGT", "SDT", "FTO", "IRAQ2" or "NPWMD".”

Note: The Department of the Treasury data sources share the same output structure 

| Field	| Description |
| ------| -------------|
| address | Entity's street/PO address |
| alt_names | Alias names used by the entity | 
| citizenships | Entity's citizenships |
| dates_of_birth | Entity's date of birth |
| entity_number | Unique id assigned by the originating list |
| ids | An array showing specific identification information of the entity. Array fields in _italics_ | 
| _country_ | _Entity's country_ |
| _expiration_date_ | _The date on which the identification will expire_ |
| _issue_date_ | _The effective date of the identification_ |
| _number_ | _Unique number assigned to the identification_  |
| _type_ | _Describes the type of identification (i.e. passport, license, etc.)_ |
| name | Entity's name | 
| nationalities | Entity's nationalities |
| places_of_birth | Entity's place of birth |
| programs | Agency program related to the entity on the list |
| remarks | Additional remarks or notes regarding the company, entity or person on the list |
| type | Classification of the entity |
| source_list_url | Location of the original list | 
| source_information_url | Information from the Source agency about the list |
| title | Entity's title |

OFAC provides [further documentation](http://www.treasury.gov/resource-center/sanctions/SDN-List/Pages/program_tags.aspx) for the **programs** field.

	
## ITA’s Process for Consolidating the Screening Lists

ITA’s data services platform imports each of the nine screening lists once a day.  It then consolidates the lists based on common field types such as name, Federal Register Notice number, and Start Date.  Not all lists contain the same fields so some search results may include more detail than others depending upon the Source agency.  Once the data services platform consolidates the lists, it publishes the [CSL API endpoint](http://api.govwizely.com/consolidated_screening_list/search).

There can be a time lag of up to one day between the time a Source has updated a screening list and when that update appears in the Consolidated Screening List API. Furthermore, the ITA Consolidated Screening List API is not the system of record for these screening lists.  Developers should strongly encourage users to refer to the website of the source agency for further instructions when finding a potential match.  Links to these websites are found above as well as in the “Source List URL” and “Source Information URL” fields that accompany each party returned in the API. 