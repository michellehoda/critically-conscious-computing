=
@keyIdeas
* Computing is not neutral; it is imbued with the values of its creators.
* Harm from data and algorithms stems partly from pre-existing systems of oppression in society at both the individual and structural levels.
* Data and algorithms can cause additional harm by amplifying, centralizing, privatizing, automating, and abstracting inequitable and unjust social systems.
* Teachers can build students’ critical consciousness of computing, equity, and justice by linking the injustices in their lives to the technology in their lives.
=

Computer science, as a discipline, has often viewed software as neutral. Algorithms, many will argue, are neutral artifacts, agnostic to the data they process. Data, many will say, are just ones and zeroes, devoid of inherent meaning. These arguments, in a way, are similar to arguments about other technologies that have potential for harm. For example, proponents of unrestricted gun rights will argue that "guns don’t kill people, people kill people," absolving the weapon from any role in killing. With the advent of the atomic bomb, many scientists viewed physics neutrally, seeing no particular role for scientists in how physics was applied. Many will use similar arguments about algorithms and data to claim that software, like guns and physics, is objective and impartial, unlike people, who may be racist, sexist, ableist, and more. Some proponents of this neutral view of computing go further, celebrating code as a savior from humanity’s inherent bias, finally freeing us from our discriminatory tendencies. This view of computing as neutral underlies the design of many of computing's most wondrous inventions: artificial intelligence was pure scientific pursuit of enabling machines to think<brooks99>; the internet was designed to connect people, for better or worse<leiner09>; even the digital computer itself was born more from curiosities of theoretical mathematicians about what was possible than any particular political viewpoint<turing09>. These intents, at least on the surface, seem prosocial and universal.

But some see in these histories, however, value-laden decisions that are inherently inequitable and unjust. Artificial intelligence was never neutral; it was always about either replacing or augmenting people, which are decidedly industrialized visions of the future of society. The internet was never neutral; its origins envisioned a future in which place and local community no longer mattered because everyone would be connected virtually<licklider63,leiner09>. And the computer itself has always been a project of war and capitalism, including a tool for winning World Wars, increasing profits in telecommunications, and accelerating business<gleick11>. And as numerous scholars and writers have shown<benjamin19,oneil16,friedman19>, the code that underlies all computational systems is inseparable from the beliefs, values, and biases of its creators, because people (and as we shall see with machine learning, data created by people) ultimately determine the behavior of software. For example, software developers working as private contractors for the U.S. [Transportation Security Agency|https://www.tsa.gov] TSA decided that security scanners would discriminate against people with gender non-conforming bodies, subjecting them to invasive, humiliating pat downs<costanzachock20>; product managers and developers at Amazon decided to sell facial recognition software to police around the U.S., even though its accuracy was disproportionately low for Black faces, the very faces being surveilled by police<browne15>. The developers of countless websites have decided that the two letter last name of this book’s first author is not a "valid" family name, preventing her from submitting web forms to access banking and social services. These anecdotes demonstrate that code and data are far from value-neutral. In fact, they are value- and bias-rich, with every line of code and every bit of data making some judgment about who people are, how they behave, and how society should work.

Of course, this is true for many technologies, not just computing. People have worried about the potential harms of television, telephones, books, and even paper. The philosopher Plato, for example, wrote on the perils of writing:

"
If men learn this, it will implant forgetfulness in their souls; they will cease to exercise memory because they rely on that which is written, calling things to remembrance no longer from within themselves, but by means of external marks.
" Plato, Phaedrus<plato72>

There are reasons to believe that computing is no different from any of the technologies in history, shaped by society and shaping society, but never ending society<bijker12>. After all, it took centuries before the printing press reshaped society<eisenstein80>, and we've only had digital computers since the 1950's. But in many ways, software may be far more powerful than any technology in history. In this chapter, we’ll discuss the powerful forces behind computing that position it for harm, and then discuss one possible method for teaching youth about these forces in ways that center their voices and experiences and develop their critical consciousness of computing.

|Chapter04_Figure01_TSA.png|A row of human silhouettes, with normative male- and female-bodied ones on the left and right with check marks above their heads, and a group in the middle with an x including people with non-normative bodies.|Computing has a way of insisting on binaries, erasing the non-binary nature of human diversity.|@jessie|

# Computing and harm

There are many ways that computing can do harm. Software might do as little as annoy or frustrate someone, and in safety critical contexts, such as flight automation, health care, or driverless cars, it might do as much as kill someone. But the particular harms of concern in this book go beyond these individual experiences with computers, to more collective concerns in society. We'll discuss three types of harm, and then examine the particular aspects of computing that often promote these harms.

## Equality, equity, and justice

First are harms of *inequality*. One way of thinking about ~equality~equality is in terms of resources and access to them. Equality, from this perspective, is the notion that everyone is given the same resources and access, regardless of who they are. In computing, this might mean that software offers the same functionality and access to everyone. For example, consider an English-only COVID-19 testing website designed for people in a local community to find the nearest testing sites. For such a website to treat everyone the same, it doesn't have to do much: as long as the website does not discriminate on the basis of who someone is, then it is treating everyone equally.

Of course, what does equal really mean? If someone cannot read English, how is it treating them the same as someone who can? If someone does not have internet access and cannot access the service, how is it treating them the same as someone who does? And in recommending testing sites, if it considers only physical distance to testing sites, but not transportation options, wouldn't it be treating people with a car, people reliant on public transportation, and people without access to either differently? Equality, in this case, results in inequity: a difference in the outcomes of a software design choice, even in the presence of equal treatment. To achieve ~equity~equity, the website might need to be translated into many different languages, offer more precise data on how long it would take to transit to a testing site, and even offer data on the cost of transportation and tests, to help people make informed decisions about where to get tested. An even more equitable solution might couple the website with transportation services, to help individuals and their families get to testing sites free of charge, so that money doesn't become a barrier to public health, or even better yet, services that involve public health staff coming to someone's home to administer a test.

But even equity has its limits. In the more equitable vision above, for example, why is it even necessary for individuals to have to find testing sites, using a website or any other means -- and why are they even sick? These are questions of ~justice~justice<sandel10>, which engage what rights to fairness people deserve and what we owe to each other. One might argue, for example, that a more just approach to COVID-19 would be for there to be a dense and robust network of community public health centers in every neighborhood in every country. If every person got their health care from such centers, and such health care was free, there would be no questions about where to get tested or how much it would cost, and no need for a website for finding testing sites. Instead, software might be used to enable public health and health care providers to focus on prevention and mobilize rapid responses to future pandemics, all built on a foundation of mutual trusting local relationships. Software _can_ be used to create more socially just worlds, it is just more often used for profit, power, and oppression.

## How computing does harm

There are many reasons why computing may have tendencies toward peril and oppression. Some of them are similar to those for any technology: in an unjust, oppressive world, technology is bound to be used for unjust, oppressive ends. However, there are specific aspects of data and algorithms that seem to make computing uniquely perilous, especially when they interact with underlying systems of oppression in society.

One aspect is computing is its ability to amplify existing sources of harm. *Amplification* is the idea that potential harm already exists in society, and is caused by people making harmful choices (often unknowingly), but technology is often harnessed to spread that harm further than one person might achieve on their own. For example, let’s return to the TSA scanner example mentioned earlier. If security checks were done entirely by human TSA agents, gender non-conforming travelers or travelers with non-normative physical disabilities might only occasionally face physical harassment by some TSA agents, but not others. The harm in this case would be limited to whatever beliefs an individual TSA agent has about trans and non-binary people. However, when the TSA commissioned machine learning-based body scanners, and created software that had embedded in it a binary notion of what a "normal" male body and a "normal" female body looked like, it shifted responsibility of judging human bodies from the diverse individual beliefs of TSA agents to a uniform standard encoded into a machine by an unrepresentative data set of human bodies. No longer was harm to gender non-conforming travelers limited to the most transphobic TSA agents, but it was now _universal_ to interactions with every TSA agent. Applications of code and data to society therefore build upon an underlying bias in society and, through the speed, precision, and reliability of code, scale that bias in ways that no technology prior has ever done.

Whereas amplification is about how code encodes inequalities, inequities, and injustices as data and algorithmic rules, and rapidly spreads it, *centralization* concerns the way that code reduces flexibility in how rules in society are interpreted. For example, let’s return to our TSA example. Prior to automated body scanners, each TSA agent dealt with the diversity of gender non-conforming or disabled bodies in different ways: some might notice that someone was disabled and decide they were not a threat; others might decide to gather more information before deciding if they were a threat, and others still, biased by ableism, might assume they were a threat. This diversity of reasoning allowed for its own kind of harm. But in creating TSA scanner algorithms, the software developers writing those algorithms could only choose _one_ set of rules by which to judge the threat that someone posed, and they chose rules that defined "normal" male bodies, "normal" female bodies, and then flagged anyone that deviated from "normal" as needing an invasive search. Centralization, in this case, eliminated the potential for TSA agents to have different ways of assessing the threat posed by people with disabilities or gender non-conforming bodies, only allowing a single set of rules that did not account for this diversity. One could argue that there are such things as "normal" bodies -- putting aside the fact that every human body is different, whether gender non-conforming or not -- but even if this were true, centralization of the rules means that no one can apply different rules, not the TSA agents or the people going through security. Centralization, therefore, is a way of taking what was previously a power distributed across all of the stakeholders in a social context, and concentrating it in an algorithm written and maintained by nameless, faceless software developers who aren’t in that social situation and may never be. If those developers make fair and just choices, then centralization can help achieve justice at greater scale; but more often, those choices are not just, and centralization makes change harder. 

A third source of harm in computing is *privatization*. This is the tendency for algorithms and data to be private goods, rather than public ones. One could imagine, for example, that the TSA algorithms and data that define "normal" could be subject to public debate, allowing for democratic processes to make them more inclusive, or even advocate for abandoning the algorithm in favor of more equitable human screening processes. But algorithms and data, when they are built in for-profit settings by private business, are not public. The TSA, for example, was created after the 9/11 attacks in 2001, as part of the U.S. Department of Homeland Security, which is overseen by the executive branch of the United States. Changing TSA policies therefore requires changing democratically elected representatives, such as the U.S. president, and members of the U.S. congress, who can create laws and orders that change the TSA’s practices. These democratic institutions, while complex, are a viable path to justice. But how does one change the source code of the TSA body scanners? The scanner hardware and software is owned and built by [Rapiscan Systems|https://www.rapiscansystems.com], a private company in California, which has no legal responsibility to make its source code available for audit and no democratic responsibility -- to the United States or any other country -- to respond to demands for change. Moreover, because it has a monopoly over scanning technology used by the TSA, it has no incentive to change its source code, even if the TSA wants it to; they can just decline, and the TSA and the government will have no recourse but to abandon its contract, halting security screening at airports. Privatization therefore shifts power away from the democratic processes to a small number of software designers and developers in private companies.

A fourth source of harm is *automation*. Whereas amplification concerns the way that the speed of computing increases the scale of its impact, centralization concerns the lack of flexibility in how algorithms follows rules, and privatization concerns who decides the rules, automation is the economic force that replaces human work with algorithms to increase productivity. Of course, automation has long been an economic force, even before computing: instead of walking, we take public transit or drive cars, and instead of hand weaving we invented looms. Today, however, most automation in the world is driven by algorithms. Continuing our TSA example, it is possible (and has already happened in many countries), that TSA agents will be replaced entirely by automated scanners. As there is less human judgment to oversee and override the injustices of algorithms, all of the other forces become stronger: privatization becomes an even bigger barrier to change, centralization puts even more importance on the source code, and amplification happens to an even greater degree. This might look like a scanner preventing anyone who does not have a "normal" body, as defined by the scanner, from ever flying on a plane. The more we eliminate human intelligence, judgment, and expertise from our social contexts, the more power is given to code and the people who write it.

A fifth force of computing that produces harm is *abstraction*. This key idea in computing, which we will return to many times in this book, is the idea of taking a complex phenomenon in the world, and eliminating nuance from it to try to capture its "essence." Humanity does this in many media. Every word in natural language, for example, is an abstraction, which tries to capture the essence of an idea: the word "duck" doesn’t nearly capture the full complexity of a real duck, but it does still usefully represent our shared concept of a duck. Mathematics also uses abstraction, reducing the complexity of an idea like "a child" to purely symbolic numbers like "1". Computing, like language and math, uses abstraction, but goes beyond language and mathematics, defining abstract representations of real world phenomena that not only model reality in abstract terms, but embed these models in social processes in the world. These abstractions come to define reality, enabling centralization, amplification, privatization, and automation. For example, the TSA body scanner algorithms can only work if it has an _abstract_ idea of what a normal human body is -- the essence of its algorithm is to detect and flag for "anomalous" bodies for further inspection, because an anomaly might be a weapon. But the scanner can’t reasonably account for every single unique detail of every human body on the planet and how it is changing. Instead, the scanners reason about an _abstraction_ of human bodies, defined by a data set that tries (and fails) to represent the diversity of human bodies. And that abstraction, rather than the actual reality of human bodily diversity, is used to decide who gets an invasive body inspection. The only way to avoid the harm of abstractions is either to find abstractions that limit harm (e.g., giving the TSA scanner a more diverse data set that fully captures our variation), or not use computers at all (which might be fine: TSA agents could just assess each individual as a unique person). Abstraction, therefore, is necessary for computing to work, and yet abstraction necessarily stereotypes and erases by ignoring detail, context, exceptions, nuance, and diversity.

None of these mechanisms of harm necessitate that computing is harmful. Perhaps the TSA body scanners do some good, possibly helping prevent terrorism, streamlining lines, sparing travelers with "normal" bodies from an invasive pat down. Moreover, some TSA agents may be quite biased in other ways (e.g., racially profiling people of color); by empowering the TSA scanners and their algorithms to determine threats, perhaps some forms of bias are avoided. Designing computing to avoid bias is therefore not a simple matter of not using computing at all -- though that should always be an option -- but rather, carefully designing computing with a rich awareness of human diversity, so that people already marginalized by society aren’t further marginalized by these computational forces. And better yet, it might mean designing computing that helps resist and dismantle the systems of oppression already in society. For example, rather than creating more software to police travelers at airports, we might create software that helps address the underlying causes of terrorism at airports, furthering dialog, diplomacy, and mutual understanding of diverse cultures globally. Such efforts would focus computing on creating a more just world, rather than one that is merely equal, or even equitable.

|Chapter04_Figure02_ChallengingConversation.png|Several hands in a circle surrounding a burst of color in the center|Conversations about diversity require time and reflection.|@jessie|

# Teaching CS, equity, and justice

Harm from computing is not inevitable. Ensuring that everyone learns how computing can do harm can ensure that we are all mindful advocates against these harms, whether citizens voting on the policy that regulates technology, or software developers and designers making choices about how software will behave. But helping youth understand the sources of harm from data and algorithms requires more than just explaining these harms -- new software is being created every day, and so youth need the skills to examine, imagine, and reason about the new computing systems that will inevitably enter their lives, posing new challenges to equality, equity, and justice.

## Research on teaching CS ethics

Most efforts to educate youth about computing at the intersection of equality, equity, and justice to date have occurred in post-secondary education, and have often been described as "ethics" courses. For decades, many CS departments at universities offered (and only sometimes required) these ethics courses, but such courses were often taught by faculty without any expertise in ethics or social justice. And because they were separate from the rest of the technical curriculum, and drew upon social science traditions instead of science and engineering traditions, students often viewed them as irrelevant to CS and their future careers as software developers<raji21>.

With the rise in visibility of ethical crises in the software industry, many in higher education have turned their attention to teaching ethics more intentionally. For example, one survey of CS ethics courses found that many CS departments have begun to innovate in CS ethics curriculum, some deepening standalone courses, others integrating ethics across curriculum, but still narrowly focusing on issues of bias and fairness, while ignoring broader human, social, and societal factors, as well as issues of what responsibility professional software developers have to make ethical choices.<fiesler20>. More recent efforts have tried to overcome this narrow focus in several ways: 

* Some have situated technical CS concepts in real-world ethical dilemmas in ways that do not detract from technical learning<fiesler21>.
* Some have positioned students as designers, responsible for taking perspectives of multiple stakeholders in real or narrative design contexts<skirpan18,bullock21>, but have found that even such situated learning does not necessarily transfer to everyday design decisions<grey21>.
* Some have partnered with experts in political science, critical media theory, and science and technology studies to provide broader and deeper exposure to how computing intersects with issues of equality, equity, and justice.<reich20,ferreira21>.

While these innovations in post-secondary methods offer some guidance to secondary, they do all tend to make one major assumption: that students have an established interest in CS and an aspiration to be a software developer or technical decision maker, directly influencing the impact of computing on society. In secondary classrooms, this not a reasonable assumption; students may have no interest in CS, and no aspiration to be a software developer, but may nevertheless care about the impact of CS on their lives. Moreover, all students should have some capacity to reason about the role of computing in their lives and society, regardless of what roles they play in society in their lives, not only because nearly every profession interacts with computing in some way, but because computing also has indirect impacts on everyone. As we discussed [earlier|pedagogy:header-7], research in secondary contexts is only just beginning to examine how to engage critical questions about computing for these broader audiences.

Following the critical CS pedagogies we discussed in previous chapters, we know that talking about equity and justice can pose some unique pedagogical challenges<ryoo20,everson22>. First, talking about justice in the context of computing necessarily may require engaging in highly-charged topics at the center of social and political conflict. Therefore, a central challenge in teaching about these topics is *identifying familiar injustices* that a diversity of students can recognize, understand, and accept as injustice, so they can do the hard work of analyzing the role of computing in that injustice. Doing this successfully means engaging richly with the injustices that might already be talked about in history, English, or social studies classes, or that students might be familiar with in their daily lives. For example, while many students may have never encountered a TSA body scanner, they might have daily experiences with misinformation on Instagram, barriers paying with cash on public transit, or the unpredictable schedules that algorithms are assigning to their parent or guardian’s shift work.

Another challenge with engaging injustice are the *difficult conversations* that such subjects may provoke. Some students may refuse to accept the existence of injustice, or insist on the objectivity of particular abstractions in the world (e.g., binary notions of gender)<oleson20>. Promoting critical consciousness about computing therefore requires preparing students for the possibility of that conflict, having norms for how to handle it, and setting clear expectations that in the short time of a classroom period or even a whole unit, disagreements might not be resolved. That is not to say that teachers should avoid these controversies, but it does suggest that choosing topics carefully can help balance the goal of developing critical consciousness of computing and the risk of destabilizing social classroom conflict.

|Chapter04_Figure03_Rules.png|A student at a desk with their head down and a blurry teacher walking away, with the block letter word "DETENTION" above and a clock that reads 10:10|Schools are a site of algorithmic oppression too.|@jessie|

## Unit sketch: Schools as a site for CS inequity and injustice

Here we present one possible unit sketch that builds upon these ideas.{We hope that readers will tell us about their experiences trying methods like these, so that we might enhance these sections with concrete examples, experiences, and insights from the classroom.} This sketch is not complete, perfect, or final, but rather a sketch that might inspire your own instructional designs and unit plans.

The essence of this example unit is to engage students in interrogating the algorithms -- or hypothetical algorithms -- in your school and how they might result in disparate outcomes for different students. Rules in schools might include things like use of the bathroom, tardiness, grading systems, or policies for late work. The advantage of classroom and school rules are that they are familiar, and may surface inequities in learning that contribute to broader inequities in society. One possible "disadvantage" -- especially if the rules interrogated are the ones in your own classroom -- is that the unit might result in actual advocacy for change (though any teacher focused on critical consciousness might want to view this as an advantage as well!).

The learning objectives of this unit sketch are as follows:

1. Students will be able to recognize rules that exist in social systems, including rules that are encoded as algorithms.
2. Students will be able to analyze how encoding rules as code might result in harmful amplification, centralization, privatization, automation, or abstraction.
3. Students will be able to explain how encoding rules as code relies on abstraction.
4. Students will be able to apply these skills to the software in their lives.

This unit is split across five sessions, the first presenting the idea of rules, and subsequent sessions engaging students in identifying the rules that govern the social context of their classroom and school. Algorithms come halfway through as a tool for potentially automating school rules, engaging youth in analyzing the potential disparate impact of that automation on their classmates.

=
### Session 1: Recognizing rules

* Begin the lesson by talking about rules and their relationship to computing, surfacing examples of the many rules in class and in school that regulate student behavior.

* Ask students to help brainstorm the many rules that they encounter and how those rules positively or negatively impact their learning and their lives more broadly.

* As students brainstorm rules as a class, write them down in a shared space, so that everyone can see them and debate how they are phrased, noting ambiguities or complexities in trying to express the rules.

* After brainstorming, engage in a dialog about the merits of the rules. Are they fair? Who are they fair to? Who are they not fair to? What are their consequences?

* End the session noting that the rest of the unit will analyze these rules, and explore the extent to which these rules should or should not be automated based on the impact that automation would have on different students.
=

The purpose of this first session is to help students see what Freire might describe as their _limiting situation_<freire68>: the social, political, and organizational context in which they find themselves, and the norms, values, and processes by which their rights are governed. The effectiveness of this dialogue should help students recognize the abundance of invisible rules to which they are subject, and also surface debates about the ambiguity of those rules, the different ways in which they are enforced, and the differential impact on students. For example, if a rule about when students may go to use the restroom arises, there may be questions about why there are limits on biological processes that a student cannot control, or if there are rules about consequences for being tardy, there may be questions about why punishments come in the form of reduced access to learning.

The second session, building upon the students’ shared understanding of their school's limiting situations, is one of focus, helping the students to connect their individual position to the rules that most affect them.

=
### Session 2: Selecting and analyzing rules

* Begin the lesson by reminding the class of the rules that were surfaced and the debates that surfaced about them, explaining that their goal is to select one of these rules and analyze it.

* After students have selected a rule, organize them into groups by the rule they’ve chosen, splitting groups to ensure group sizes of no more than four (even if some groups analyze the same rule).

* *Formative assessment*. Prompt students to analyze, as a group, 1) the primary benefits of the rule, and who receives them, 2) the primary harms of the rule, and who suffers them, and 3) the ambiguities in the rule and how rule enforcers navigate those ambiguities.  Students should produce a short presentation summarizing these insights.

** This assessment is _responsive_ because it gives students agency to choose the rule they want to examine.

** To ensure that it is _participatory_, negotiate with students what their presentations might contain, adding or removing elements they want to discuss.

** This assessment is _educative_ because the prompt to present necessitates analysis, creating a social context in which students share their analysis.

* Once students are ready, have each group present their analyses to the class, revealing the varying ways that the rules are impacting different stakeholders and being enforced. Solicit constructive feedback from their peers, recognizing insights and identifying observations, and identifying benefits and harms they might have missed.

* Have students return to their groups and use what they learned from their peers to expand or refine their analysis.

=

The use of groups in these analyses is critical to helping students understand the diverse perspectives and experiences that students might have in relation to a rule. For example, students analyzing rules about tardiness might notice that some students are reliant on parents to drive them to school, but some parents are unreliable. Other students might be dependent on publication transportation, which is usually reliable within some window, but sometimes there are outlier days that cause tardiness. Prompting students to connect these diverse contexts to enforcement helps them imagine how the rule is enforced, and how the enforcers might not understand these diverse contexts. The class-wide sharing of analyses of other rules will broaden students’ critical consciousness of school rules further. Students should leave this session seeing their classroom and school in a new light, as a system of rules that may or may not be equitable, and of enforcers who are placed in the position of making challenging judgments about when and how to enforce rules.

The next session turns the students’ attention toward computing, challenging them to imagine a future in which the rules they have analyzed are automated.

=
### Session 3: Automating rules

* Remind students about the rule they have selected and ask them to review their analysis from the previous session, returning to the groups from the previous session.

* Introduce the idea of computation as a way of encoding rules so that they may be quickly, reliably, and automatically checked. Offer an example of a rule that is already checked by software, such as rules about graduation and passing grades, or high stakes exams.

* *Formative assessment*. Prompt each team to imagine a software system that automates the rule, without fundamentally changing the rule: What would the exact rule be? How would it be checked automatically? How would the consequences of the rule be enforced or communicated to a person to enforce? Students should create a short presentation to describe their design to their classmates.

  ** This is _responsive_ because it gives creative agency to students to imagine the rules they want.

  ** To ensure it is _participatory_, give students an opportunity to broaden the scope of how much time students will have to present and how presentations will run.

  ** This is _educative_, because it creates a social context in which to share their creative ideas that incentivizes envisioning.

* Once students are ready, have each group present their design to the class for critique. Prompt the students in the audience to identify the strengths and weaknesses of the software relative to the current human enforcement of rules. Each team should capture notes about the discussion.

* After the discussion, connect the discussion to ideas of amplification, centralization, privatization, abstraction, and automation, explaining each concept, and connecting them to the automation concerns that students raised.
=

This session requires students to shift their mindset from _critic_ of rules to _designer_ of rules, enforced by software. This is a critical mindset shift, as it requires them to orient to finding a solution that would work, while accounting for the known problems with the existing rule, and trying to avoid creating new problems through automation. This will tend to create a defensive stance, as they’ve invested effort in design; the group critique of the idea will help them see the consequences they may have overlooked. This will help them develop empathy for the tensions between creatively designing automation and avoiding harm.

The next session calls students to decide what to do: automate the rule, reject automating the rule, discard the rule, or some other course of action.

=
### Session 4: Advocating

* Have students return to their groups and bring up their rule analysis, automation design, and critique notes.

* *Summative assessment*. Explain to students that the goal for the final day is to decide what to do about the rules. Prompt them to discuss with their teams: should the rule be automated, should they stay with the status quo, or should the rule be changed, or perhaps discarded altogether? As they discuss, they should add to their presentation a proposal for a course of action. The final presentation will be submitted for summative assessment.

  ** To ensure the assessment is *responsive*, commit to making changes to the rules based on students’ proposals.

  ** To ensure the assessment is *participatory*, co-construct a rubric for evaluating their final presentations, discussing what would make a good presentation.

  ** The assessment is *educative* because it challenges students to develop concrete proposals for change.

* Once students are ready, have them present a final time to the class their proposed course of action. After each presentation, if there is consensus to do something other than the status quo, solicit ideas from the class about how they might advocate for that change. If there is no consensus, facilitate a discussion about whether the rule deserves further debate, to try to find consensus.

* End the session with a reflection on how algorithms fared in the discussions. Were there rules for which algorithms were agreed to be beneficial? What about those rules or designs prevented algorithms from causing further harm? If algorithms were almost always doing more harm than good, when should algorithms be used to automate rules, if ever?
=

This session shifts students’ role again, putting them in the position of policy maker rather than designer or critic. This is critical in helping students recognize the complexity of deciding how and whether to deploy computing into social contexts, and helping them develop nuanced views of when and if computation provides added value.

The last session focuses on transfer, from the school context to broader society, challenging students to identify other software systems in their lives that are having similar impacts on them and others.

=
### Session 5: CS and society

* Explain the ideas of amplification, centralization, privatization, automation, and abstraction, linking them to the issues surfaced in the presentations, and explaining examples of other contexts in society in which these forces occur.

* Prompt them to individually reflect on the software in their lives, and how it might be playing a similar role that some of the school rule automation might play. What harms might that software be doing to them or their friends and family?

* After brainstorming, ask students to select the one idea they brainstormed that they are most concerned about, and prepare a few talking points for a short verbal presentation.

* Ask each student to present their concern.

* After all students have presented, summarize what they have shared, reminding them of key questions to ask about computing: who decides, who benefits, who is harmed, and what are the underlying systems that computing is amplifying, centralizing, privatizing, automating, and abstracting.

* *Summative assessment*. Close the unit by evaluating students' final presentation against the co-constructed rubric, and offering feedback about students’ analysis of the implications of automation rule enforcement.
=

This unit positions students not only as critics of computing, but also critics of oppressive social systems in general, while also giving them experience in the role of designing social contexts, and advocating for social change. Throughout, it grounds their understanding in the particular powers of computing, hopefully helping them see the computers in their lives no longer as innocuous, neutral objects, but powerful machines for enforcing social rules. The unit also works well as a priming for more involved design projects, where students must make more detailed and complex design decisions.

# Conclusion: Balancing utopian and dystopian futures of computing

When talking to students -- and really anyone -- about the intersections between computing and justice, it is easy to seem pessimistic. After all, there are so many ways that computing is doing harm, to so many people, and these stories are often so invisible in education, marketing, and the media, it can feel necessary to make space dialog these harms. 

But there are reasons to balance these conversations with optimism. First and foremost, computing _can_ be used for social good: it is helping us accelerate discoveries of life saving medications and treatments, it is enabling people with temporary and permanent disabilities to gain independence, and in countless ways, it is empowering youth to express themselves, organize, and advocate in ways that simply were not possible. Any discussion of the failures of computing should be balanced with its successes, to reinforce that we all have agency to shape how computing is used. 

But there is another reason to make space for optimism: computing alone cannot achieve equality, equity, and justice, and framing it purely as an obstruction to justice erases the possibilities of using it as a tool for justice. Raising questions about how computing does harm is an opportunity to talk about more equal, equitable, and just futures, and reposition computing from a technology that is neutral or in the way, to a technology that might be harnessed for justice.

@standardsHeader
@standardsBlurb

@cstaHeader
@cstaIC
@csta2IC20
@csta2IC21
@csta3AIC24
@csta3AIC25
@csta3AIC27
@csta3AIC28
@csta3BIC25
@csta3BIC26
@csta3BIC28

@toleranceHeader
@toleranceDiversity
@tolerance9
@toleranceJustice
@tolerance12
@tolerance13
@tolerance14

@teacherHeader
@teacher1
@teacher1a
@teacher1f
@teacher3
@teacher3b
@teacher5
@teacher5a
@teacher5c
@teacher5d
@teacher5e