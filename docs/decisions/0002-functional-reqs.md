# Functional Requirements

The functional requirements described in this document represent an high-level idea of what we can expect
from a platform like PeopleAsk.
Depending how the project will evolve, some of the requirements listed here could be changed, rethought or even dropped.
Similarly, more requirements could be added as well.

## Definitions

- **Signing service**: is the service that authenticates individuals
  willing to sign the text of a petition on an instance of PeopleAsk.
  Normally, each country offers a domestic authentication service for its citizens.
  The service must provide an API to allow an eligible citizen to sign
  an arbitrary text.
  Obviously, said service must be well known and legally accepted in the country
  where the petition is being issued.

- **Signature**: is the unique digital signature computed over the petition's text
  by a recognized citizen.
  In order to be legal, and thus to be formally accepted by the government,
  a signature must be computed using an accepted service in the country where the
  petition is being issued.

## Context and Problem Statement

PeopleAsk is intended to provide a private platform for issuing public petitions.
PeopleAsk must allow signers to produce legal digital signatures on the petition's text.
The method used to produce the signatures must be recognized and accepted
by the country's institutions.
The users must be able to consume an instance of PeopleAsk as a web application reachable though Internet.

We identify three logical distinct groups of users:

- **Casual users**
- **The organizers**
- **The signers**

### Casual users

Casual users want to:

1. Read the petition's text.
2. Know how the petition is going.

### The Organizers

The organizers propose their petition throughout one instance of PeopleAsk.
The organizers take care of the infrastructure that hosts the PeopleAsk instance,
both on-prem and in the cloud.

The organizers financially bear the costs deriving from getting the infrastructure that hosts
the platform and the costs deriving for the use of a certain signing service.

The organizers want to:

1. Get the infrastructure and deploy an instance of PeopleAsk on it.
2. Login into the deployed instance of PeopleAsk and get an administrative dashboard.
3. Formulate the petition's text.
4. Choose the signing service to be used by the signers.
5. Start the petition.
6. Close the petition.
7. Collect the gathered signatures once the petition is closed.

### The signers

This group is the one willing to sign the petition issued by the organizers.

The signers want to:

1. Sign the petition's text.
2. Leave a contact to be informed of the petition's outcome.

### PeopleAsk's Functional Requirements

The application provides specific functionalities for each user category.

### Functionalities for the casual user

1. The user interacts with the application through the web browser inserting the URL that points to the PeopleAsk instance.
2. The user sees the petition's text and a button below asking to sign.
3. The user sees the petition's progression.

### Functionalities for the organizers

1. An instance of PeopleAsk must be deployable as an Helm chart onto
   a Kubernetes cluster.
2. Once installed, a fresh instance of PeopleAsk must show an initial
   page from where the organizers set the organizers's password.
3. Once the password has been set, the organizers must be able to login into the administrative dashboard.
4. From the administrative dashboard must be possible to:
   - Set the petition's text.
   - Choose a signing service and configure it.
   - Start the petition.
   - Stop the petition.
   - Collect the gathered signatures.

### Functionalities for the signers

1. The signer clicks on the button below the petition's text and starts the signing process.

## Considered Options

Not applicable.

## Decision Outcome

Not applicable.
