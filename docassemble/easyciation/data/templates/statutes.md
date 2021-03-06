[BOLDCENTER]Articles of Association

[BOLDCENTER]${ association.name }

%if association.has_logo:
[CENTER]${association.logo}
%endif

[STOP_INDENTATION]

[PAGEBREAK]

# GENERAL PROVISIONS

**Art. 1 Denomination**

% if (association.is_political and association.is_religious): 

${ association.name } is an association according to the present articles of incorporation and the articles 60 CC and following of the Swiss Civil Code.

% else:

1. ${ association.name } is an association according to the present articles of association and the articles 60 and following of the Swiss Civil Code.

% if association.is_political:
2. The Association is independent from any religious affiliation.
% elif association.is_religious:
2. The Association is independant from any political affiliation.
% else:
2. The Association is independent from any religious or political affiliation.
% endif

% endif



**Art. 2 Duration and headquarters**

% if association.is_limited_period:
The Association is established until the ${ association.end_date }
% else:
The Association is established for an unlimited period of time.
% endif

The headquarters of the association are in the canton of: ${ association.canton }.

% if "ZH" in association.canton:
The address of the associaiton is : ${ association.address }
% endif



**Art. 3 Purpose**

1. The association has the following purposes:

[//]: # (this is... a hack)
[//]: # (without this loop, primary_goal is asked first)
[//]: # (causing docassemble to crash)
% for goal in association.goals:
% endfor

a. ${ primary_goal }
% for goal in association.goals:
% if goal != primary_goal:
a. ${ goal }
% endif
% endfor




**Art. 4 Resources**

The Association’s resources come from: 
  a. donations and bequests  
  b. sponsorship  
  c. public and private subventions  
  d. contributions from members  
  e. and any resources authorized by law  



**Art. 5 Exercise Period**

The association's exercice period is of one calendar year.  

# MEMBERSHIP

**Art. 6 Membership**

1. The Association can at any time admit new members.
2. Individuals or legal entities who have demonstrated their commitment to the purpose of the association may apply for membership.
3. Each application for membership must be made in writing and addressed to the Committee who will decide on the outcome of the application.
4. In the event of a refusal, the rejected member may appeal against this decision before the General Assembly, substantiating his claim and within ten days of being notified of the rejection.
5. The decision shall take effect at the end of the exercise period. In exceptional cases, it may take effect immediately.
6. The appeal validly submitted shall be added to the agenda of the next General Assembly for consideration. The General Assembly shall hear the Committee on the reasons for its refusal and shall decide on the disputed application. The Committee shall abstain from voting.
7. A qualified majority of two-thirds of the votes of the General Assembly is then required to admit the appeal and, in doing so, the application. 

**Art. 7 Loss of Membership**

1. Membership shall be lost by:
    a. death ;
    b. written resignation addressed to the Committee at least six months
    before the end of the exercise period, except in exceptional
    circumstances;
    c. expulsion;
    d. non-payment of membership fees for more than one year.
2. The Committee may exclude a member for good cause. This exclusion may be appealed to the General Assembly under the same conditions as an appeal for refusal of membership.
3. Members shall have no right to the assets of the Association. In no case may they claim reimbursement of the paid membership fees.
4. The association's assets alone shall be liable for commitments entered into in its name.
5. Members of the Association shall not incur any personal liability for the liabilities of the Association.

**Art. 8 Bodies**

The Association shall have the following bodies:
a. General Assembly
b. The Committee
c. The Auditors

# General Assembly

**Art. 9 Definition**

1. The General Assembly is the supreme body of the Association. It is composed of the members of the Association.
2. The General Assembly shall meet once a year in ordinary assembly. It may also meet in extraordinary assembly whenever necessary at the request of the Committee or of at least one-fifth of the members. The General Assembly may also be held online if the technical means are available to guarantee compliance with voting procedures.
3. The General Assembly shall be validly constituted regardless of the number of members present.
4. Any member unable to attend the General Assembly may be represented by another member by means of a written proxy given to the representative. Each member may only represent a maximum of two other members. The representatives are obliged to respect the wishes of the represented members regarding the decisions to be taken.
5. The Committee shall call the General Assembly by notifying each member of its date and agenda in writing at least 21 days in advance.
6. Members may submit individual proposals to the agenda insofar as they are received by the Committee within 14 days of the General Assembly. The Committee shall verify their admissibility and inform the members of any changes made to the agenda at least 10 days before the General Assembly.
7. An ordinary meeting may become a General Assembly, by means of universal assembly, when all the members of the Association are present or represented and when they unanimously consent to it.
8. The President shall chair the General Assembly. If absent, he/she shall be replaced by another Member of the Committee.

**Art. 10 General Assembly Competences**

The General Assembly is, among others, competent for the following matters:

% for competence in association.general_assembly.competences:
% if association.general_assembly.competences[competence]:
a. ${ competence }
% endif
% endfor

m. other items on the agenda

**Art. 11 Agenda of the General Assembly**

The agenda of the ordinary General Assembly shall necessarily include:
a. The approval of the minutes of the last General Assembly;
b. A report on the activities of the Association during the past exercise period;
c. The reports of the treasurer and the Auditors;
d. The adoption of the budget;
e. The discharge and election of the members of the Committee and of the Auditors when necessary;
f. Individual proposals.

**Art. 12 Majority and Quorum**

1. Decisions of the General Assembly shall be taken by a simple majority of the votes of the members present. The President has the casting vote.
2. Decisions concerning the amendment of the articles of association and the dissolution of the Association may only be taken by a majority ${ association.general_assembly.qualified_majority_threshold } % of the members present. The same applies to appeals against refusals of membership and members exclusions.
3. Decisions votes by an assembly with less than ${ association.general_assembly.quorum_threshold } % of members present are not valid. 

**Art. 13 Voting procedures**

1. Only members of the association have the right to vote.
2. Voting shall be held by show of hands. At the request of a member, voting shall be held by secret ballot.
3. Abstentions shall be counted in the total number of votes based on which the majority threshold for approving a decision or resolution of the Association is calculated.
4. Invalid votes shall not be counted in the total number of votes based on which the majority threshold for approving a decision or resolution of the Association is calculated.
5. The President has the casting vote.
6. Any member who has a conflict of interest with a decision or resolution to be made by the General Assembly or any other body of the Association shall be excluded from voting.

# The Committee

**Art. 14 Composition**

1. The Committee is the governing body of the Association. It shall be composed of at least a President and a Treasurer.
2. The Committee is composed of a minimum of ${ association.committee_minimum_number } and a maximum of ${ association.committee_maximum_number } natural persons elected by the General Assembly, including at least a President and a Treasurer.
3. At least one member of the Committee, with power of signature, shall reside in Switzerland.
4. The duration of their mandate is of one-year renewable.
5. For each position, the candidate who obtains the greatest number of valid votes cast shall be elected. In the event of a tie, a second round shall be held to decide between the candidates.
6. The term of office shall begin at the end of the General Assembly at which the member was elected.
7. The term of office shall end upon expiry of the mandate, dismissal, resignation, incapacity to act or death of the Committee member.

**Art. 15 Competences**

The Committee shall be responsible for :

% for competence in association.committee.competences:
% if association.committee.competences[competence]:
a. ${ competence }
% endif
% endfor



**Art. 16 Organisation**

1. The Committee shall meet as often as the business of the Association requires.
2. As a collegial body, the Committee shall endeavour to take its decisions by consensus. Where consensus cannot be reached, decisions shall be taken by a majority of the votes cast. In the event of a tie, the President shall decide.

**Art. 17 Resignation**

When, following a resignation, a minimum of three members of the Committee is not reached, the Committee shall elect a member of the Association to take over the vacant position, on an interim basis, until the next General Assembly.

# The Auditors

**Art. 18 Composition and Functions**

1. The Auditors shall be appointed by the General Assembly for a period of one year. They may be re-elected a maximum of 1 time.
2. The Auditors are two members of the Association who are not Members of the Committee nor performing any task delegated by the latter.
3. At the end of each exercise period, they shall verify the legality and correctness of the balance sheet and accounts drawn up by the Committee. It shall present its finding in a report for the General Assembly.
4. It may request all supporting documents from the Committee. If he/she deems it necessary, he/she may request that an extraordinary General Assembly be convened.

# Miscellaneous

**Art. 19 Committee remuneration**

1. The members of the Committee shall act on a voluntary basis and shall only be entitled to compensation for their actual expenses and travel costs. Attendance fees may not exceed those paid for official committees. For activities which go beyond the usual scope of their function, each member of the Committee may receive appropriate compensation.
2. Paid employees of the Association may only sit on the Committee in an advisory capacity.

**Art. 20 Powers of signature**

In principle, the Association can only be validly bound by the collective signature of two members of the Committee.

**Art. 21 Dissolution**

1. In the event of the dissolution of the Association, the available net assets shall be entirely donated to an institution pursuing a purpose of public interest similar to that of the Association and benefiting from tax exemption.
2. Under no circumstances may the assets be returned to the founding members or to the members, nor may they be used for their benefit in whole or in part and in any way whatsoever.

**Art. 22 Accounting**

1. The Association's accounts shall be kept by the Committee. The accounting records and other supporting documents shall be kept for a period of 5 years.
2. The financial year corresponds to the exercise period of the Association.

**Art. 23 Forum and applicable law**

Any dispute, controversy or claim arising out of or in connection with these Articles of Association, including their validity, nullity, breach, or dissolution, shall be resolved before the courts of ${ association.canton } - respectively the Federal Court - in accordance with Swiss law.

**Art. 24 Entering into force**

1. The present articles of association were adopted by the constitutive General Assembly on the date of ___________________________.
2. They shall enter into force on the date of their approval.

**Art. 25 Displays and Communication**

One copy of these articles of association shall be signed and kept in the archives of the Association and may be consulted by third parties.

[BEGIN_TWOCOL] First signatory [BREAK] Second signatory [END_TWOCOL]

