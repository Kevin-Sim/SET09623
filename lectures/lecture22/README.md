# Lecture 22: Legal Issues

In this lecture we will examine the legal frameworks important to software engineering.  These are:

- Computer Misuse.
- Data Protection.
- Intellectual Property.

As a caveat, I am not a lawyer nor do I have any legal training.  I have done my best to present the information objectively.  Do not treat any information presented as legal advice or opinion.

## Behavioural Objectives

- [ ] **Describe** the *elements of computer misuse*.
- [ ] **Describe** the *principles of data protection*.
- [ ] **Describe** *intellectual property rights in regards to software.*

## Computer Misuse

The [Computer Misuse Act](https://en.wikipedia.org/wiki/Computer_Misuse_Act_1990) was introduced in 1990.  The act targets cyber crime, including hacking, data harvesting, and ransomware.  The act specifies three types of offences:

1. Unauthorised access to computer material.
2. Unauthorised access with the intent to commit further offences.
3. Unauthorised modification of computer material.

These three offences cover several crimes, for example:

- Searching through password permutations (e.g., brute-forcing) to access a system, even if the attempt is unsuccessful.
- Encrypting someone else's data and demanding compensation to retrieve the data (ransomware).
- Performing a denial-of-service attack.
- Writing and circulating a computer virus or worm.
- Creating a fake service to collect user data (phising).

These offences can lead to imprisonment or 6 months to 10 years depending on the offence, and a potentially unlimited fine.  The challenge is proving culpability of the defendant.  Proving intent is difficult.  Furthermore, the wording of the act means certain industry practices (e.g., time-locking software) can be considered illegal.  However, the act has been used as a model in other countries.

Our discussion on security in [Lecture 23](../lecture23) will analyse attack types.  As IT professionals part of your job is to protect against such attacks.  If you were found to be complicit in a breach of this act it has serious repercussions.  A BCS member would be struct off, their chartered status revoked, and any query to the BCS about the person would inform that the member had been struck off.  The ACM have similar requirements.  This is one of the key foundations of a professional body.  It is also one of the guarantees from a member and to a member.

## Data Protection

Data Protection focuses on an individual's rights to know, access, and modify data held against them by an organisation.  It also ensures protection of said data.  As data protection focuses on a citizen's interactions with organisations, the offences can carry significantly large fines for the organisation in breach.

There have been two pieces of UK legislation on data protection:

- Data Protection Act 1998.
- Data Protection Act 2018.

Note that data is **not** only that stored on a computer.  Data includes any representation, including paper files or photographs.  Our discussion will be in a computer context, but it is worth remembering the scope of these acts.

### Data Protection Act 1998

The original [Data Protection Act](https://en.wikipedia.org/wiki/Data_Protection_Act_1998) was enacted to implement the European Union Data Protection Directive 1995.  The aim was to provide individuals with the right to control data about them.  Domestic use of data - such as having a list of names and emails - did not fall under control of the act.

#### Scope of Protection

A person who has their data processed has the following rights:

- to view the data an organisation holds on them for a reasonable fee.
- request that incorrect information be corrected. If the company ignores the request, a court can order the data to be corrected or destroyed and compensation awarded.
- require that data is not used in any way that may potentially cause damage or distress.
- require that their data is not used for direct marketing.

The reasonable fee was quite small: £2 for a credit agency; £50 for medical and educational; £10 otherwise.  The Freedom of Information Act that followed in 2000 reflects the attitude that access to certain data should have minimal cost to an individual.

#### Data Protection Principles

The original Data Protection Act defined eight principles:

1. Personal data shall be processed fairly and lawfully.
2. Personal data shall be obtained only for one or more specified and lawful purposes.
3. Personal data shall be adequate, relevant and not excessive in relation to the purpose or purposes.
4. Personal data shall be accurate.
5. Personal data processed for any purpose or purposes shall not be kept for longer than is necessary.
6. Personal data shall be processed in accordance with the rights of data subjects (individuals).
7. Appropriate technical and organisational measures shall be taken against unauthorised or unlawful processing of personal data and against accidental loss or destruction of, or damage to, personal data.
8. Personal data shall not be transferred to a country or territory outside the European Economic Area unless that country or territory ensures an adequate level of protection for the rights and freedoms of data subjects in relation to the processing of personal data.

Personal data is defined as data relating to a living individual who can be identified

- from that data.
- from that data and other information in the possession of, or is likely to come into the possession of, the data controller.

Sensitive personal data concerns the subject's race, ethnicity, politics, religion, trade union status, health, sex life or criminal record.

Consent is defined as:

> …any freely given specific and informed indication of his wishes by which the data subject signifies his agreement to personal data relating to him being processed.

## Data Protection Act 2018 and the General Data Protection Regulation (GDPR)

The [General Data Protection Regulation](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation) has greater implications than the previous Data Protection Act.  The aim of GDPR is protection of EU citizen data, providing said citizens with greater control of their personal data.  The Data Protection Act 2018 is broadly similar to the Data Protection Act 1998, and was introduced prior to full implementation of GDPR.  The 2018 act ensures GDPR is met in the UK.

GDPR affects any organisation offering goods and services to EU citizens.  Any organisation holding personal data on EU citizens can be held accountable under GDPR no matter where in the world they are based.  Personal data is anything that can be linked to an individual, including:

- name.
- address - both physical and email.
- photos.
- IP addresses.
- social media information and posts.
- etc.

In short, any information that can be used to determine your identity is covered by GDPR. Furthermore, for children 16 and other parental consent is required to process their data.

Some terminology to get your head around:

- A **data controller** is a person who determines how personal data is or will be processed.
- A **data processor** is a person (not employed by the data controller) who processes data for a data controller.
- **Processing** is obtaining, recording or storing information or data.
- A **personal data breach** is a breach of security leading to unauthorised access to personal data.

A full discussion of GDPR is not possible here, but you should make yourself aware of the details available [here](https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/).  GDPR has major effects to your work as an IT professional no matter where in the world you work.  Knowing, understanding, and complying with GDPR is important.  If a known data breach is not reported within 72 hours the maximum fine is the greater of:

- 4% of organisational global turnover.
- €20 million.

Furthermore, the Information Commissioner's Office can enact the following further sanctions:

- Issuing warnings and reprimands;
- Imposing a temporary or permanent ban on data processing;
- Ordering the rectification, restriction or erasure of data; and
- Suspending data transfers to third countries.

As an IT professional, your responsibility is to support your organisations compliance under GDPR.  No organisation can manage the maximum fines available.  You have a duty to report problems (just as defined under professionalism in [Lecture 21](../lecture21)) and to ensure that no problems occur.

### Individual Rights Under GDPR

GDPR defines eight rights to individuals:

1. The right to be informed.
2. The right of access.
3. The right to rectification.
4. The right to erasure.
5. The right to restrict processing.
6. The right to data portability.
7. The right to object.
8. Rights in relation to automated decision making and profiling.

More information can be found [here](https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/individual-rights/)

## Intellectual Property

Wikipedia defines [Intellectual Property](https://en.wikipedia.org/wiki/Intellectual_property) as:

> Intellectual property (IP) is a category of property that includes intangible creations of the human intellect.

In other words, IP is property which comes from creative thought.  IP incorporates the following:

- Copyright.
- Patents.
- Trademarks.

We will examine copyright and patents as the two relevant forms of IP in software development.  Trademarks are concerned with marketing and brand and therefore not of interest here.

### Copyright

You wouldn't steal a movie?  That was the old advert that targeted film *piracy* and copyright infringement.  This advert was legally incorrect as copyright infringement is not theft.  In the UK:

> Basic definition of theft:
>
> 1. A person is guilty of theft if he dishonestly appropriates property belonging to another with the intention of permanently depriving the other of it; and "thief" and "steal" shall be construed accordingly.
> 2. It is immaterial whether the appropriation is made with a view to gain, or is made for the thief’s own benefit.

Point 1. is the important one: *intention of permanently depriving*.  Downloading a movie does not permanently deprive anyone of their property.  In fact, theft is considered a criminal offence in the UK whereas copyright is a civil matter.

Copyright deals with intellectual property protection and the laws exist to support individuals and organisations making civil cases.  From [Wikipedia](https://en.wikipedia.org/wiki/Copyright):

> Copyright is a legal right, existing in many countries, that grants the creator of an original work exclusive rights to determine whether, and under what conditions, this original work may be used by others.

Copyright concerns the rights of ownership for creators of creative works.  This includes books, music, movies, and software.  The code you write is protected under copyright.  In the UK, code is considered a literary work, and therefore copyrighted until the death of the author plus 70 years - long after your code will be obsolete.

However, copyright does not protect ideas, procedures, methods of operations, or mathematical concepts.  An app idea is not protected under copyright.  It may be patentable which we will look at that soon.

There are some fair use reasons where copyrighted work can be used:

- Private and research study purposes;
- Performance, copies or lending for educational purposes;
- Criticism and news reporting;
- Incidental inclusion;
- Copies and lending by librarians;
- Format shifting or back up of a work you own for personal use;
- Caricature, parody or pastiche;
- Acts for the purposes of royal commissions, statutory enquiries, judicial proceedings and parliamentary purposes;
- Recording of broadcasts for the purposes of listening to or viewing at a more convenient time;
- Producing a back-up copy for personal use of a computer program.

Basically, personal use or educational use normally allows copyrighted work to be reproduced.  However, you should always consider whether you have the right to make a copy for your intended purpose.

#### Who Owns Your Work?

Normally you or the team you are working with retains copyright.  However, when you work for an organisation they will normally retain copyright as you have produced work under their employ.  This is usual - the organisation has paid you to produce work for them.  You should read your contract to determine exactly what your employer is claiming ownership over.  

Freelance and consultancy work is retained by the author unless an agreement has been made otherwise (e.g., a contract).

Copyright can be transferred and sold to another party also.  However, copyright cannot be claimed for any work that is a copy of previous work.  For example, a quote from another text is retained by the original author.

### Patents

From [Wikipedia](https://en.wikipedia.org/wiki/Patent):

> A patent gives its owner the right to exclude others from making, using, selling, and importing an invention for a limited period of time, usually twenty years.

Patents are about protecting an idea rather than a creative work.  For example, if you design a better CPU, you will want to protect that idea so you can make the most money from it.  Patents aim to protect inventions.

Patents are typically applied to physically realisable ideas.  [Software patents](https://en.wikipedia.org/wiki/Software_patent) are an evolving field, but typically a program cannot be patented in most of the world.  The US is different.  A key element is the definition of a program: a form of algorithm.  As an algorithm is a mathematical idea, and this cannot be patented as they are considered already to exist and are just discovered.  However, it is not as clear cut.

In the UK, *programs for computers* are not patentable as defined in law.  In other words, computation is not patentable.  Implementing a business process as a piece of software is such an example.  However, if a program makes a significant, non-obvious, part of a technical solution it might be patentable.  A control system for an industrial process might be patentable.

As with copyright, any patents will normally be claimed by your employer.  Depending on your organisation, they may seek patents in the US where such things are easier.  Some organisations may give a bonus for patentable work as long term it provides a competitive advantage to the organisation.

### Licensing

As a software engineer you need to be aware of software licensing.  Partly because any personal work you do should have a license added to it (such as we did in GitHub), but also to understand how you can use other's code and how you must provide attribution to the original authors.

Wikipedia provides a handy diagram illustrating the levels of software license:

<p><a href="https://commons.wikimedia.org/wiki/File:Software-license-classification-mark-webbink.svg#/media/File:Software-license-classification-mark-webbink.svg"><img src="https://upload.wikimedia.org/wikipedia/commons/3/38/Software-license-classification-mark-webbink.svg" alt="Software-license-classification-mark-webbink.svg" height="152" width="640"></a><br>By shaddim / <a href="//commons.wikimedia.org/w/index.php?title=Mark_Webbink&amp;action=edit&amp;redlink=1" class="new" title="Mark Webbink (page does not exist)">Mark Webbink</a> - <a rel="nofollow" class="external free" href="https://www.redhat.com/f/summitfiles/presentation/May31/Open%20Source%20Dynamics/Troan_OpenSourceProprietyPersp.pdf">https://www.redhat.com/f/summitfiles/presentation/May31/Open%20Source%20Dynamics/Troan_OpenSourceProprietyPersp.pdf</a>, Public Domain, <a href="https://commons.wikimedia.org/w/index.php?curid=45955580">Link</a></p>

The following table defines these different licence levels:

| Rights granted | Public domain | Permissive FOSS license (e.g. BSD license) | Copyleft FOSS license (e.g. GPL) | Freeware/Shareware/Freemium | Proprietary license | Trade secret |
| ------------------- | ----- | ----- | ----- | ----- | ----- | ----------- |
| Copyright retained  | No    | Yes   | Yes   | Yes   | Yes   | Very strict |
| Right to perform    | Yes   | Yes   | Yes   | Yes   | Yes   | No          |
| Right to display    | Yes   | Yes   | Yes   | Yes   | Yes   | No          |
| Right to copy       | Yes   | Yes   | Yes   | Often | No    | Many lawsuits are filed by the owner |
| Right to modify     | Yes   | Yes   | Yes   | No    | No    | No          |
| Right to distribute | Yes   | Yes, under same license | Yes, under same license | Often | No | No |
| Right to sublicense | Yes   | Yes   | No    | No    | No    | No          |
| Example software    | SQLite | Apache web server | Linux kernel | League of Legends | Windows | Games by Rockstar |

The standard open source licenses are summarised [here](https://en.wikipedia.org/wiki/Comparison_of_free_and_open-source_software_licenses).

As a software engineer, it is your responsibility to ensure you are using software and code correctly.  Your employer is liable for any licensing decisions you make as an employee.  Therefore, you must know how you can use the software you are considering using and ensure any licenses and attributions are correctly made.

## Summary

In this lecture we have examined some of the legal ideas that impact software development.  In particular, we have:

- Described the elements of computer misuse, specifically unauthorised access to computer material.
- Described the principles of data protection, examining the General Data Protection Regulation.
- Described intellectual property rights in regards to software, covering copyright, patents, and licensing.