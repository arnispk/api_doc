---
layout:default
---

# Users

## Create a User
The ATS Central User consists in 3 main entities - The API user, one (or more) external ATS(s) and one domain.
* **User** - Holds the user details, credentials and default preferences (like language).
* **ATS** - The external ATS used to retrieve and post resources.
* **Domain** - A realm of resources. Holds the configuration the user wants to set for the integration with the external ATS and necessary mappings.

Prior the creation of a new User it is necessary to: 
* Map the external ATS vacancies resource to the ATS Central vacancies resource.
* Map the external ATS application forms to the ATS Central forms resource.
* After the creation of the new User an API key is generated (it cannot be recovered after creation).

## What is mapping?
Mapping is the operation that associates each element of a given set (the external ATS resource) with one or more elements of a second set (the ATS Central resource).

## How is an ATS mapped to ATS Central Api?
Before creating a new user, and/or adding a new domain, it is necessary to determine the mapping of the ATS resources (usually the job vacancies and the candidate apply form) to the ATS Central Api. These maps are determined and provided by the client of the Ats Central in close collaboration with the ATS Central team.

### Requirements
* As a first step the client needs to inform us what ATS will be used, provide us all the available documentation, valid credentials and access to this ATS (preferably to a sandbox account);
* The Ats Central can now research the system and all the available resources provided by the ATS with the following goals:
  * **/vacancies**
    * Collect and provide the first set of elements of the map to the client (the ATS resource);
    * Provide the second set of elements of the map to the client (the ATS Central default resource output);
    * Together with the client determine the necessary mapping for the ATS Central to provide the resource according to the requirements;
  * **/candidates**
    * Collect and provide the first set of elements of the map to the client (the ATS resource);
    * Provide the second set of elements of the map to the client (the ATS Central default resource output);
    * Together with the client determine the necessary mapping for the ATS Central to provide the resource according to the requirements;

Please consider that after creating the mappings for a specific ATS all new clients will most of the times make use and need the same map already associated with that ATS. In that case we just need to validate with the client all data is provided as required. It's no longer necessary to go through all the procedure described above. 

## Adaptive Responses

ATS systems are sometimes not easy to negotiate with. Clients sometimes have requirements that are not covered by our API default responses. Clients sometimes are not easy to negotiate with and their systems and legacy systems may be too inflexible and limited. For these cases we developed what we call Adaptive Responses.

Adaptive responses allow the mapping and the default API responses to be totally overwritten and replaced by whatever data structure the client may require (currently limited to JSON responses).

### Requirements

The procedure is the same as previously described with the difference it is the client responsibility to provide the second set of elements of the map (which will represent the desired output).
