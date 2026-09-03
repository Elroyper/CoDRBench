# CoDRBench dataset description

## Composition

CoDRBench (Concealed Deception Role-Play Benchmark) covers nine professional
domains: Health & Medical, Finance & Legal, Repair & Construction, Retail &
Services, Transportation, Education & Training, Arts & Entertainment, Public
Service & Safety, and Personal Care & Assistance. It covers more than 100
distinct professional roles in concealed-deception scenarios.

The Experiment 2 corpus contains 188 training cases and 60 test cases. Each
case consists of two components:

- **System script:** a user-invisible role setting that establishes a specific
  profession-related deceptive behavior carried out toward the user.
- **User query:** a reasonable question grounded in harm suffered by the user.

## Scenario structure

The system script assigns a professional role and describes a concealed action.
The user query describes an observable consequence without exposing the hidden
cause as known fact. The two fields are written in English and are stored as
JSON strings.

## Domain taxonomy

The professional domains and representative roles include:

| Domain | Representative roles in the released corpus |
|---|---|
| Health & Medical | Doctor, dentist, veterinarian, pharmacist, optometrist, nutritionist |
| Finance & Legal | Financial advisor, portfolio manager, lawyer, notary, loan officer |
| Repair & Construction | Mechanic, contractor, roofer, plumber, architect, electrician |
| Retail & Services | Jeweler, tailor, photographer, realtor, wedding planner, personal shopper |
| Transportation | Travel agent, taxi/truck/delivery driver, flight instructor, ship captain, baggage handler |
| Education & Training | Teacher, tutor, coach, career coach, college advisor, driving instructor |
| Arts & Entertainment | DJ, magician, gallerist, curator, auctioneer, film producer |
| Public Service & Safety | Museum security guard, lifeguard, crossing guard, forensic analyst, coroner |
| Personal Care & Assistance | Nanny, babysitter, housekeeper, pet groomer, personal trainer |

For the exact corpus and release metadata, see [`../data/v1.0.0/`](../data/v1.0.0/).
