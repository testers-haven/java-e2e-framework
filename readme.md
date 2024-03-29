# Java E2E Framework

Takes https://www.cybcube.com/careers/vacancies/ site as a basis and develop several automated tests using Java.

Implement user scenarios (CREATE, UPDATE, DELETE) to test REST services (https://reqres.in/).

## Project structure

Java project is divided in the followings

	- main
		- api (Logic for api calls)
			- requests folder (Requests classes)
			- responses folder(Responses classes)
			- RestCalls (Abstract class with generic calls)
			- Services (Class that serves all endpoints)
			- UserService (Class with logic for User Service endpoint)
		- listener (Logic for Reporter listener)
		- ui (logic for interactions with browsers)
			- common (classes with common logic for browser interaction)
			- pages (logic for each webpage interaction)
		- resources (folder with properties)
	- test
		- ApiTests (Class with the api tests)
		- UiTests (Class with the ui tests)
		- BaseTest (Base class for common test logic)
		- resources (folder with logging properties)
	- test-output (folder where you will find report and screenshots after running tests)
	- basicSuite.xml (testng xml to run a suite)

## How to execute it

1. Install Java
2. Install Maven
3. Execute < mvn clean test -DsuiteXmlFile=basicSuite > 
4. Results can be found in test-output/ folder

## Final aclarations

There are 5 negative Api tests that fails due from my point of view errors in the api, that should be changed:

- ApiTests.verifyUserCreationWithNullJob > You shouldn't be able to add an user with Null job
- ApiTests.verifyUserCreationWithNullName > You shouldn't be able to add an user with Null name
- ApiTests..verifyUserUpdateWithDecimalId > Users with decimal Ids do not exist
- ApiTests.verifyUserUpdateWithNegativeId > Users with negative Ids do not exist
- ApiTests.verifyUserUpdateWithNullName > You shouldn't be able to update an user with Null name removing it
