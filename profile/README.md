Introduction to Health Place 

Health Place has been created to make it easy for people to access the support opportunities they need and want. 

It is possible to create a local version of Health Place covering a range of support opportunities or create a nationwide vertical (or beyond) focusing on one sector in depth. 

Health Place currently has 27 code repositories, which deliver three main blocks of functionality: 

An information base of support opportunities that includes: a) a core database; b) tools for owners of support to edit their listings; c) tools that automate the process of keeping listings up-to-date; d) a range of ways for users to access support. 
A pathway processor that automates processes of screening and prioritizing people for support and expediting their access to this support. 
A proto-personal care plan that summarises the support people need, want and are accessing 

Creating your own information base 

Creating a new instance of Health Place is easy for any competent developer:

Run the API code on a local machine
Run the Front End code on a local machine
Run the Cloud Formation stack.
Set up and run a new AWS-hosted instance 

Steps 1-3 should take around 30 minutes.  The time required for Step 4 will depend upon requirements.  

More bespoke work is required to run the code on Azure or other hosting services. 

Customising your information base 

You can select from the ‘Components’ repository to find a comprehensive range of design components that can be used as required to change the look and feel of your website. 

You can of course also design a new interface as is required, but this will require more cost and effort.  You may wish to focus in the first instance on changing the front-end experience for the public and leave the current designs for organisational users unchanged.   



Updating the information base 

Any information base is only as good as the freshness and accuracy of its data. The platform offers a mix of capabilities for making the data as up-to-date and accurate as possible. These include: 

Full provider control of listings of support opportunities
Roles and permissions for trusted individuals and organisations to add and maintain data
The ability to pull on third-party APIs 
The ability to scrape data from any source
Automatic checking of addresses 
Automatic review of keywords/taxonomy mapping 

The platform has begun to leverage both its own base language model/knowledge graph as well as Chat GPT 4.  This supports 99% automated ingestion of new support opportunities.  

There is scope to further leverage the use of Chat GPT or similar to keep listings up to date. 

Data standards 

At the heart of the platform is a set of keywords or taxonomies that serve both as a knowledge graph and as a large language model. The knowledge graph defines the relationships between different taxonomies so that their meaning is understood and thus that data can be managed more efficiently and also that support can be accessed more easily. This includes the use of large language models. 

It is the focus on data standards - along with attention to the specialist user experience - that makes this service superior even to new use of Open AI and similar tools. 

Options for supporting ‘search’ 

The use of data standards as above means that support can be searched for / discovered through a variety of methods that include the following: 

Google style search - requires the use of Open Search functionality 
Simple or more complicated quizzes that ask questions and generate tailored results
Filters to generate more tailored results 
Carousels of commonly requested results cf Netflix
Integration with conversational AI/chatbots
Integration with search engines etc 
Embedding of any of the above by I Frames/widgets in others’ websites. 


Enhancing the core code base 

The platform tracks any ‘bugs’ in the current platform. It supports automated ‘testing’ of new features.  It lists ‘new requirements’. It offers a ‘developer forum’. Above all it supports the build of new functionality. 

For the Information Base, the majority of the relevant code can be found in the ‘API code repository’.  Admin roles and permissions can be found in the ‘Provider Admin’ repository. 

The platform has a Restful API that can be used to integrate with any other data services that conform to standard Restful API requirements. These can be open, closed or commercial, depending on the use case in question. 

The intention is to build out a range of new integrations, each of which adds great added value.  These will be found in a new ‘Integrations’ code repository. 

The Pathway Processor 

So far we’ve focussed on the Information Base, but the platform also supports engagement with end users through a structured process - a ‘pathway’ - that is driven by access to structured data about people. 

In principle it is possible to create any kind of pathway, for any group of people, as long as relevant data is available. 

To create a new Pathway first select the ‘Pathways’ repository and add a ‘new pathway’. 

You then need to ensure that you have access to the required data. You can view other examples of data that are set out in both a Google sheet version (to allow review by subject experts) and a JSON version (to allow a developer to create a live version). 

You then need to select and add a series of ‘States’. These are the logical steps in your pathway that each person will go through. It is possible to create sub-steps or alternative steps, depending on the characteristics of different segments of target users. This offers easy, almost unlimited customisation using simple javascript commands, that can be mocked up in the first instance in a Google sheet. Simple Yes / No (Boolean) reasoning is used to progress people through the relevant steps.   

Data is stored in a data store and new facts about people can be pulled as needed, normally on a daily basis, to keep it updated. 

Data is consumed by a ‘pathway database’ and processed by the pathway on a daily basis.

Note. Currently this data is limited to data about patients that conforms to a number of FHIR resources, but in principle can be extended to any set or linked sets of data. These new resources will need to be edited/added within the ‘patient data ingestor’. 

Personal care record 

The platform currently has a simple Personal Care Record system that allows a user to create an account, protect it with two factor authentication and store basic information that includes information about needs, plans and support accessed. 

The Personal Care Record can be linked by NHS number and embedded within third-party systems. 

Use of third-party services 

The platform currently leverages a range of third-party software services, as set out below. 

AWS (for hosting plus other optional plugins) 
Apify (for scraping of data using our bespoke Actor)
Graphologi (for the curation of our taxonomies/knowledge graph)
Google (for validation of postcode against latitude and longitude) 
Chat GPT 4 (for checking of meaning in free text by leveraging our knowledge graph) 
Contentful (for serving up blocks of content and support options in a modular and customisable way). 

Plus other services as needed, such as for automated testing of code quality. 
