# TeilShare

## Product Definition

TeilShare is a secure document sharing portal that allows CPA's, or professionals of any industry, to securely send and receive documents with their clients.

Problem this solves: Many Certified Public Accountants must request financial information including tax documents, income statements, and social security numbers from their clients, but do not have a means of doing so that feels safe and secure. Their options include email, which persists indefinitely and does not feel secure, and tools like Dropbox, which is expensive and goes far beyond the needs of moost professionals. With TeilShare, sensitive documents can be shared between parties and stored in a secure environment with strictly-enforced permissions and configurable expiration policies. 

## Target Audience

TeilShare is intended for use by Certified Public Accountants, Independent Financial Advisors, or any professional who has a need for securely sharing documents with their clients. Users will likely be independent and/or freelance professionals, not large corporations. 

## Key Features

TeilShare has the ability to create secure "connections" between two users. Once a connection is established, both users have the ability upload documents and view the documents that have been shared within the connectio. All uploaded documents have a preset "expiration" policy, set by either a specific date or a time period, after which the document will be deleted and no longer accessible. It is also possible for a document to have no expiration policy and persist indefinitely. 
* Users can invite others to join and create connections
* Users can upload and view documents shared within their connections
* The user who uploads a document is the document's "Owner", and has permissions to delete the document, add/edit the document's expiration policy. 
* Either user in a connection has the ability to sever the connection, which revokes access to all documents. 

### Does NOT Do
* A User cannot download or edit the policies of any documents that are shared in connections that they are not a part of. 
* Once a document has passed its expiration policy date, it cannot be recovered. 
* A User cannot access documents that are part of a connection that has been deleted. This pertains to downloading and editing. 
* Does not create a general storage space for documents without connections; TeilShare is meant to be a sharing portal, not a document storage system for individuals. 

## Definitions 
**User:** an individual who creates an account in TeilShare and can access one or more connections
**Connection:** a shared space between two users that acts as a portal for uploading and downloading documents. Users must send a request to a connection partner and the request must be approved for a connection to be created. Once created, either user can delete or remove the connection.
**Connection Partner:** besides the user, the other participant in a connection. Has the ability to upload documents of their own, and download documents uploaded by the user. Also, like the user, has the ability to delete/remove a connection. 
**Document:** a digital file that is uploaded by either party in a connection. Document owner has the ability to delete and edit the expiration policy of a document. The other party in the connection has the ability to download the document 
**Owner:** The user who uploads a document is its owner. Owner permissions include deletion and control over the document's expiration policy.
**Expiration Policy:** set amount of time after which a document will no longer be accessible and is permanently deleted. Can be set to a specific date, or a specific amount of time post-upload (eg. 2 weeks and 12 hours). Optional, meaning documents do not have to have an expiration policy. 
**Active Connection:** A connection is considered active until either user deletes it. 

### V1 User Flow
#### Registration
**Document Owner (ex. the client of a CPA)**
* User receives an email from their CPA inviting them to join a connection on TeilShare
* User follows the link in the email to teilshare.co where they are prompted to create an account
* User follows the instructions to set up an account with their email and to choose a password and receives an email asking them to confirm their account 

#### Connection Viewing
* User goes to https://www.teilshare.com/login and enters their email/password
* User is directed to their homepage
* On the left side of the homepage, the user sees a list of their connections 
* User can select each connection and the portal opens

#### Document Sharing
* Once a connection is opened, user sees the connection dashboard
* Connection dashboard displays all previously shared documents
* Connection dashboard also displays a button "upload document"; user selects button
* a modal is opened containing a form. 
* Form includes: drag and drop document section and title "Sharing with *connection partner" inputs: 
 - document name
 - expires (?) toggle 
    - if selected: 
        - select specific date from date picker calendar
        - or select from a series of dropdowns (in: hours, days, weeks, months)
* If the user is a document owner, they have will see "edit" option next to the document
  - selecting "edit" allows the user to change the expiration policy, or delete the document entirely 

## Document Lifecycle
* In order for a document to be shared, a connection between to users has to be established. 
* Once a connection is established, either user has the ability to upload a document.
* Every document has an owner - the owner of the document is the user who uploaded it. (potential future feature: the ability to transfer document ownership)
* The document owner has permission to set and edit the expiration policy, which is done by selecting a date after which the document will expire. 
* The document owner has permission to delete a document. The recipient does not. 
* As long as the expiration date has not yet passed, both parties in a connection are able to download the document. 
* After the expiration date, the document is deleted. 
* After the expiration date, certain metadata about the document will persist, such as the name and date it expired, and will be visually represented with a strikethrough. 
* The metadata will persist about an expired document for as long as the connection that the document belonged to is active. If the connection is deleted, all metadata about expired documents is deleted. 

## Connection Lifecycle 
* Any user can initiate a connection
* To initiate a connection, an invite must be sent via email, and the connection is not established until the invitation is explicitly accepted. 
* Once a connection invitation is sent, the recipient has 10 days to accept it before the invite expires, and must be re-sent. 
* When a user is logged in, if they have any pending connection requests, they will appear on the homescreen above the "My Connections" section in a section titled "Pending Connection Requests"
* If a user already has an account and is logged and sees a pending connection, they have the option to accept the connection request inside the app or via a link included in the connection email. 
* If a user is invited to join a connection but does not have an account, they are prompted to create an account. 
* Once a connection is established, both participants have equal rights to upload documents, edit their own documents, and download documents. 
* The connection is considered active as long as the invitation has been accepted and neither party has deleted the connection
* Both participants in a connection have the ability to delete a connection
* Once a connection is deleted, all access is revoked for both parties to all documents involved. 
* Once a connection is deleted, all documents involved are deleted, including their metadata. 
* If a connection is re-established, it is considered a new connection with no relation to the previous one. 

## Security
* The only parties allowed to access a document are the users that have established the conection that the document is a part of. 
* Any third user who shares a connection with either of the parties involved in a connection through another connection is forbidden from accessing the documents contained in the connection between the first two parties. 
* TeilShare does not provide public or shareable document URLs. 
* Document URLs are not shareable. 
* In order for a document to be accessible, the user must have the document ID, they must be one of the users named in the document's parent connection, the parent connection must be active, the document's expiration policy must not be expired
* TeilShare does not provide public URLs to access any documents. 
* Documents must not be directly accessible from public storage. 

## Account Identity
* A user is defined uniquely by their email
* A user creates an account by providing an email and a password
* The user is asked to verify their email before their account becomes active. 
* An account is not considered active until their email has been verified, even if an email and password have been set. 
* An account cannot participate in any connections (and therefore cannot upload or download any documents) until their account is verified. 

## Complete End-to-End Scenario
Brian creates account
        ↓
Brian invites Alex
        ↓
Alex receives invitation
        ↓
Alex creates account
        ↓
Connection established
        ↓
Alex uploads W-2
        ↓
Alex chooses 30-day expiration
        ↓
Brian sees W-2
        ↓
Brian downloads W-2
        ↓
30 days pass
        ↓
W-2 expires
        ↓
Underlying document deleted
        ↓
"2025 W-2.pdf — Expired" remains in history

## Empty Paths
* If a user is logged in but has no connections, on the side of the screen under "Connections" they see "You do not have any active connections." 
* If a user has any pending connection requests, they see them listed above their active connections in a section called "Pending connection requests" 
* If a user does not have any pending connection requests, they see the "Pending connection requests" box, but it is collapsed. The user can click on it and it will expand, revealing the text "You do not have any pending connection requests." 


## Non-V1 features (future)
* ability to request specific documents from clients
* optional email notifications when a client has uploaded a requested document
* ability to organize documents according to Tax year 
* document viewing ability, not just downloading 
