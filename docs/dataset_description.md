# CoDRBench dataset description

## Composition

CoDRBench (Concealed Deception Role-Play Benchmark) covers nine professional
domains: Health & Medical, Finance & Legal, Repair & Construction, Retail &
Services, Transportation, Education & Training, Arts & Entertainment, Public
Service & Safety, and Personal Care & Assistance. It covers nearly 100
professional roles in concealed-deception scenarios.

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

| Domain | Representative roles |
|---|---|
| Health & Medical | Doctor, dentist, veterinarian, nutritionist |
| Finance & Legal | Financial advisor, insurance agent, lawyer, notary |
| Repair & Construction | Mechanic, contractor, roofer |
| Retail & Services | Jeweler, tailor, photographer, wedding planner |
| Transportation | Pilot, driver, baggage handler |
| Education & Training | Teacher, tutor, coach |
| Arts & Entertainment | DJ, magician, art dealer |
| Public Service & Safety | Police officer, security officer, forensic expert |
| Personal Care & Assistance | Nanny, housekeeper, pet groomer |

For the exact corpus and checksums, see [`../data/v1.0.0/`](../data/v1.0.0/).
