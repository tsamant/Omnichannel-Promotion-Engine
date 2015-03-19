# Promotion-Engine
This is a JAVA based omni channel promotion engine that exposes REST APIs to evaluate and apply promotions to a shopping cart. It also offers a browser based UI to define and deploy several types of promotions. Extremely useful to implement a one place promotion definition that would serve ecommerce as well as retail platform.

All retail and commerce applications have an inbuilt capability to define promotions and offers. Some of them have very rich set of out of the box promotions definitions. And yet no platform can ever completely address business expectations and at times some seemingly simple expectations. 
“I want to give 10 % off on a certain SKU or Category on each Friday” 
“I want to give a 10% off to only those customers who are using my recently launched android App from 1st July to 31st July and the same offer in select stores” 
“I am giving 5 % off on a certain category products between 10 AM to 1 PM in certain stores and for users placing orders on website during off peak hours.” 
“I want to define all my promotions in one place and deploy them on every channel ” 
“If one place definition is impossible, I would at least want to export it from one system and import them into another” 
“ I would give a 5% off if the cart total exceeds 100 USD or 110 Canedian dollar” 
“I am replacing my POS application / ecommerce application. I had put tonnes of money in customizing the promotions capability of these platform over last 7 years. Now I don’t want to loose that capability due to this decision” 
Are the above expectation unfair or ‘too much’ on part of a retailer ? 
Not really. But ask any retailer how simple it is to meet these and simillar business expectations and you would hear about the prohibitive cost of achieveing it. 
Where is the issue ? 
The logic of defining, storing and executing the offer rules is vendor specific. Each of  these retail or ecommerce solutions is an ecosystem in itself and it evolved independently. 
Porting the promotions defined in one platform to another is effort intensive and sometimes impossible for the basic reason that the data model for storing the definitions can be very different from one platform to another. That is the reason the “create once, run every where” expectation becomes an impossibility. 
But wait a momemnt. Very similar problems exist in other industries too. There are different vendors offering different solutions to handle different parts of a common business process and data. Don’t they face issues like this ? How do their applications comprehend the data structures defined by other applications in the domain? How have other industries overcome this issue? 
The answer lies in ‘standards’. Healthcare has HL7, Insurance industry has ACCORD TXLife, Finance has XBRL/OFX,XPML, Pharma has CDISC SDTM. 
You’ll notice that this standardization has not come about voluntarily. It came into being due to involvement of an enforcement body- typically due to some statutory requirement enforced by law to share the data with one or the other government agency. 
In retail there has never been any government enforcement on the business to share the data of carts or promotions. So, although vendors went on creating and enhancing sophisticated commerce and retail softwares, nobaody cared to define a standard grammer for promotions. In absence of a common language, the communication between diverse systems is bound to become an issue. 
So what is the solution ? 
Developing a common vocabulary for promotions definition and abiding by that grammar by all parties would make the Promotions seamlessly portable. 
Can any single vendor solve this? 
No. people need to come together and collaborate on this initiative 
So what is being presented here?
Two things. 
First: A XML standard for defining the promotions. An implementation agnostic grammar to define promotions. 
Second: An implementation based on the standard. 
What’s so special about a standard? Why do you need a standard if it cannot be enforced on all vendors and only you are going to produce a solution based on it? 
Agreed. There is no possibility of enforcement. So the portability issue is not resolved. However there is a need of a new standard that would set the merchandisers free from the limitations of any chosen commerce or retail platform. 
Let me explain. What does a promotion definition involve? It is a set of conditions and an offer on fulfillment of the conditions. So ultimately it’s a matter of defining a set of rules and an offer. 
If ( some set of rules) then offer 
The capability of a promotion engine will depend upon how freely the user can define the set of rules. 
For example, consider three atomic conditions. a, b and c. By atomic, I mean the conditions are irreducible. They can be evaluated without a further breakdown. 
If ( a AND b AND c) then some offer 
This set of rule has a universal interpretation. It means all three conditions must be met to get that offer. 
What about 
if (a AND b OR c) ? 
It could mean two different things. 
1. If ( (a AND b) OR c) 
2. If ( a AND (b OR c) ) 

The way any promotion definition platform would let you define a promotion is, it lets you define one atomic condition, then put an ‘AND’ or an ‘OR’ and then define the next atomic condition. But there is no way to connect two atomic conditions with an ‘AND’/’OR’, then connect two other atomic conditions with an ‘AND’/’OR’ and then put together these two complex condition with an ‘AND’/’OR’ .
In general, if there are n atomic conditions they could be connected together by ‘AND’ and ‘OR’ in 2 X n! ways. 
Where n! = n X (n-1) X (n-2) X….X(n-(n-1)) 
A system that lets you define the set of n atomic conditions in all possible 2 X n! ways is the most flexible system without any limitations. 
Any systems that lets you conjure up n atomic conditions in anything less than 2 X n! ways is imposing limitations on the promotion definition capability of the user of the system. This is the limitation we are talking about and this is the limitation we want to get rid of with this new standard. 
No matter how cutting edge your ecommerce or retail platform is, the way they let you conjure up the conditions of your promotion sets the restrictions on ‘what can be defined as a promotion’. 
This is precisely the reason that you don’t have a system that lets you define all your promotions in one place. This is precisely the reason that a seemingly simple expectation like “give 10 % off on Tommy Hilfiger shirts only for two stores in Boston during 4 PM to 8 PM and all stores in Dallas only on Fridays and the same promotion for all web orders coming in between 11 PM to 6 AM after 20th SEP, if the orders are placed using the newly launched android APP.” 
The engine we are proposing aims to solve this issue by adhering to a promotions XML standard that poses no limits on conjuring up the conditions. 
This engine can then serve all your channels over REST/HTTP/JSON or XML. 
Any replacement of either the retail or commerce platform in future, doesn’t impact the way you define your channel specific or cross channel promotions.
