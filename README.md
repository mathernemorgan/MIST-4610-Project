# MIST-4610-Project

**Team Name:**
Group B4

**Group Member Names:**
Zeynep Koseoglu (Conceptual Modeler), Mark Monzer (Database Designer), Morgan Matherne (Group Lead), Roshan Gadiraju (SQL Writer), Hiya Shah (Data Wrangler)

**Case Description**
LMC is an organization that organizes many music events in Athens. It partners with artists and venues to plan shows and manage events. They keep track of significant information regarding venues. This could be location, venue capacity, and the status of partnership with venues. It can also store data regarding artists' contact information or where they’re based. Each event represents a unique performance, venue, and time. Events can have many artists. For example, an opener and headliner, and all artists are given a unique performance order. All events are managed by a head/main staff member, alongside a backup staff member. Additionally, LMC handles equipment like sound and lighting systems, which are appropriately distributed as needed. These resources are tracked closely to ensure no double bookings. LMC also tracks partnerships and agreements for shared equipment. To make the system more efficient, we added a band and social media extension. Artists can be connected to bands, allowing the system to represent groups and solo artists. We also added social media tracking. This allows each artist to have data such as followers, likes, views and monthly listeners across many platforms. These extensions aid LMC in making better decisions when planning events and booking artists. An example would be choosing more popular artists for larger venues or more fitting time slots. Overall, the system LMC uses data to improve its business as opposed to just managing events.

## Data Model
![LMC Database Model](Group%20B4%20-%20LMC%20Database%20Model.png)

## Data Dictionary
![Data Dictionary B4](Data_Dictionary_B4_long.png)

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

Find Resource Types that have NEVER been used
Question: Which resource types have never been used in a show allocation?
Justification: Dead stock shows up clearly, managers might choose to sell off old gear. Or they could group it with popular items so event spaces are more likely to book them. Seeing what sits too long helps shape those choices.

<img width="1988" height="1508" alt="image" src="https://github.com/user-attachments/assets/339827b7-3aab-43be-9a43-51257390578c" />


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

**Database Information**

