# MIST-4610-Project

**Team Name:**
Group B4

**Group Member Names:**
Hiya Shah (Conceptual Modeler), Mark Monzer (Database Designer), Morgan Matherne (Group Lead), Roshan Gadiraju (SQL Writer), Zeynep Koseoglu (Data Wrangler)

**Case Description:**
LMC is an organization that organizes many music events in Athens. It partners with artists and venues to plan shows and manage events. They keep track of significant information regarding venues. This could be location, venue capacity, and the status of partnership with venues. It can also store data regarding artists' contact information or where they’re based. Each event represents a unique performance, venue, and time. Events can have many artists. For example, an opener and headliner, and all artists are given a unique performance order. All events are managed by a head/main staff member, alongside a backup staff member. Additionally, LMC handles equipment like sound and lighting systems, which are appropriately distributed as needed. These resources are tracked closely to ensure no double bookings. LMC also tracks partnerships and agreements for shared equipment. To make the system more efficient, we added a band and social media extension. Artists can be connected to bands, allowing the system to represent groups and solo artists. We also added social media tracking. This allows each artist to have data such as followers, likes, views and monthly listeners across many platforms. These extensions aid LMC in making better decisions when planning events and booking artists. An example would be choosing more popular artists for larger venues or more fitting time slots. Overall, the system LMC uses data to improve its business as opposed to just managing events.

## Data Model
![LMC Database Model](Group%20B4%20-%20LMC%20Database%20Model.png)

**Core Entities and Relationships:**
The database model represents the operations of the Live Music Circuit (LMC) by capturing relationships among venues, events, artists, staff, and production resources. A Venue can host many ShowEvents, while each ShowEvent occurs at exactly one Venue, forming a one-to-many, non-identifying relationship. Venues may also be affiliated with other venues through the VenueAffiliation entity, which models a recursive many-to-many, non-identifying relationship and stores details such as affiliation type and duration. Each ShowEvent is coordinated by one main staff member and one backup staff member, creating two separate one-to-many, non-identifying relationships from Staff to ShowEvent. Artists and ShowEvents have a many-to-many relationship resolved through the associative entity ArtistBooking, which is identifying (composite key of event_id and artist_id) and captures attributes such as performance order and format. Resource management is handled through ResourceType, ResourceItem, and ResourceAllocation: a ResourceType has many ResourceItems (one-to-many, non-identifying), and ResourceItems are assigned to ShowEvents through ResourceAllocation, which creates a many-to-many relationship between ShowEvent and ResourceItem via two one-to-many relationships. In this model, ResourceAllocation uses its own primary key, making these relationships non-identifying, and stores timing details such as load-in and return times.

The model is extended to include artist structure and digital presence through Band, SocialMedia, and ArtistSocialMediaMetrics. A Band can have many Artists, forming a one-to-many, non-identifying relationship that allows representation of both solo performers and group members. SocialMedia defines platforms, and ArtistSocialMediaMetrics serves as an associative entity between Artist and SocialMedia, creating a many-to-many, identifying relationship (composite key of artist_id and socialmedia_platform). This entity captures metrics such as followers, streams, and engagement, enabling analysis of artist popularity. Overall, the design uses associative entities to resolve many-to-many relationships, distinguishes between identifying and non-identifying relationships based on key dependency, and separates event scheduling from resource allocation to accurately reflect real-world operations while supporting meaningful managerial insights.

## Data Dictionary
![Data Dictionary](Data_Dictionary_Final_long.png)

# Queries

**Query #1**

Identify all "All-Ages" Venues in Athens
Question: Which venues in Athens allow all-ages attendance, and what are their capacities and addresses?

Justification: It lets booking agents pick places suited for younger crowds, matching the audience an artist draws. Venue fit matters when age groups differ. That way, shows land where fans actually go.

<img width="1896" height="986" alt="image" src="https://github.com/user-attachments/assets/13221753-9ac5-4d1b-94fa-d3d64e73b26c" />


**Query #2**

List all Bands within a specific Genre
Question: Can we see a list of all bands categorized as ‘Hip-Hop’ and where they are from?

Justification: Organizers can rely on this during festivals to sort acts by sound, especially when setting up dedicated rap events across collaborating spots. What matters is how it helps shape each night’s lineup without confusion spreading behind the scenes.

<img width="1896" height="986" alt="image" src="https://github.com/user-attachments/assets/bb4d67f9-de2b-4fa8-addc-f953c1540e52" />


**Query #3**

Retrieve all Resource Items with a "Fair" Condition
Question: Which equipment items are currently in "Fair" condition?

Justification: Equipment shows signs of aging, the crew can decide what needs fixing or swapping out first. This helps avoid breakdowns when performances are happening. Spotting issues early means problems won’t interrupt a show. When parts start wearing down, they get attention before things go wrong. That way, everything runs smoother on event nights.

<img width="1896" height="1296" alt="image" src="https://github.com/user-attachments/assets/7b7668c7-5e92-4377-a399-9665eff9e129" />

**Query #4**

Find Artist contact info for those based in Athens
Question: What are the names and phone numbers of all artists based in Athens?

Justification: A handy list of nearby performers lets organizers act fast when spots open up unexpectedly. This setup cuts down on travel expenses while making it easier to pull together community-based shows at short notice.

<img width="1896" height="664" alt="image" src="https://github.com/user-attachments/assets/745de363-8772-486b-bbe1-af601fc4f40d" />


**Query #5**

Calculate Potential Rental Revenue based on Venue Partner Type
Question: What is the total potential rental revenue for each venue, accounting for different rates for Partners vs. Non-Partners?

Justification: It shows how each location is doing financially, managers can see whether offering discounts through partners brings enough extra business to make up for lower prices. What matters here is spotting trends across sites where deals might be helping - or hurting - overall results. When one spot gives more breaks but sells way more tickets, that pattern could signal success. Yet another place might cut prices just a bit yet stay flat, raising questions about what drives growth. Seeing these differences clearly helps leaders adjust without guessing.

<img width="1988" height="1286" alt="image" src="https://github.com/user-attachments/assets/e3ee8161-d47d-4aa7-a0ea-12e0fcb6bf18" />


**Query #6**

Identify "Power Artists" (Booked for more than 2 shows)
Question: Which artists have been booked for more than two shows across the circuit?

Justification: Who pulls big crowds and delivers steady income? These top performers often get first pick on dates or deals covering several shows. Some find their calendar fills fast - consistency pays off.

<img width="1988" height="1292" alt="image" src="https://github.com/user-attachments/assets/8fdc70ed-6041-4469-a373-e6464f9d3b7e" />

**Query #7**

High-Usage Equipment Audit
Question: Which specific resource items have been allocated to more than three different show events, and what is their current condition rating?

Justification: Heavy-use gear shows up clearly here. When something gets called on often but isn’t in top shape, trouble looms mid-show. Spotting these pieces helps teams plan upkeep ahead of time. Rotation becomes easier too - spreading use so some units aren’t worn down while others gather dust. One piece working hard while rest wait? That pattern breaks with this view.

<img width="992" height="661" alt="Screenshot 2026-04-10 at 4 16 45 PM" src="https://github.com/user-attachments/assets/74c4b1f1-cfa5-4387-889b-c001948f47ec" />

**Query #8**

Staff Workload: Primary vs. Backup Roles
Question: What is the total distribution of Primary and Backup coordinator roles across all staff members?

Justification: Balancing tasks matters so one person does not end up carrying too much weight. Team flow stays smoother when responsibility shifts around naturally. Work spreads out better if no individual gets stuck leading every time. Even pressure helps keep energy steady across roles. Shared effort means fewer breakdowns during busy periods.

<img width="1988" height="1336" alt="image" src="https://github.com/user-attachments/assets/b9c5d7b7-df7b-4211-86ea-a4cee49e6225" />


**Query #9:**

Identify Social Media Engagement vs. Performance
Question: How does an artist's monthly listener count correlate with their actual number of bookings?

Justification: It shows which artists are gaining fast on social media, even if they’re not playing many gigs yet. Scouts spot these names before others catch on. Popularity online sometimes means big crowds later. A quiet artist today might sell out tomorrow. Numbers help tell that story early.

<img width="1988" height="1286" alt="image" src="https://github.com/user-attachments/assets/885311ae-1e4d-4579-8de2-7db883a771c1" />


**Query #10**

Average Slot Order by Venue (Multiple JOINs)
Question: What is the average performance slot position for artists at each venue?

Justification: What you see reflects how busy things get at certain spots. When numbers climb, it often means several acts play one after another there. That kind of setup usually needs extra help around the location. Single-act places tend to run with fewer people on hand.


<img width="1988" height="1504" alt="image" src="https://github.com/user-attachments/assets/c3ccb123-66fa-438e-8332-db03d8ec4696" />

**Query Matrix Table**

<img width="627" height="370" alt="PNG image" src="https://github.com/user-attachments/assets/e420c645-e6f8-4e4b-80ce-ffcf4c4c81ac" />


**Database Information**
Name of Database: mb_B4
Additional Information: All project queries are bookmarked and saved as stored procedures in MySQL using the required GP_Qx naming format:
CALL GP_Q1
CALL GP_Q2
CALL GP_Q3
CALL GP_Q4
CALL GP_Q5
CALL GP_Q6
CALL GP_Q7
CALL GP_Q8
CALL GP_Q9
CALL GP_Q10





