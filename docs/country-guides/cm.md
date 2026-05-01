# Cameroon (CM)

**Licensee:** *(contact Darrel Technologies Ltd)*  
**Currency:** Central African CFA Franc (XAF, FCFA)  
**Timezone:** Africa/Douala (WAT, GMT+1)  
**Language:** French (primary), English (Anglophone regions)  

---

## Social Security & Payment Modes

| Setting | Value |
|---------|-------|
| Social security scheme | CNPS |
| POS payment modes | Cash, Orange Money, MTN Mobile Money, Bank Transfer, Cheque |

---

## Bilingual Context

Cameroon has two official languages and two parallel education subsystems:

| Subsystem | Language | Exam body |
|-----------|----------|-----------|
| Francophone | French | MINESEC / OBC |
| Anglophone | English | GCE Board (Cameroon) |

For Anglophone schools, change `DEPLOYMENT_LANG` to `en` and configure grading scales appropriate for O-Level / A-Level.

---

## Academic Structure

### Francophone subsystem

| sERP Division | Level | Classes |
|---------------|-------|---------|
| Maternelle | Préscolaire | Petite, Moyenne, Grande Section |
| Primaire | École primaire | SIL, CP, CE1, CE2, CM1, CM2 |
| Collège | Collège | 6ème, 5ème, 4ème, 3ème |
| Lycée | Lycée | Seconde, Première, Terminale |

### Anglophone subsystem

| sERP Division | Level | Classes |
|---------------|-------|---------|
| Nursery | Nursery | Nursery 1, 2 |
| Primary | Primary | Class 1–6 |
| Secondary | Secondary | Form 1–5 |
| High School | High School | Lower Sixth, Upper Sixth |

---

## Assessment Framework (`francophone_basic`)

| Setting | Value |
|---------|-------|
| CA weight | 40% |
| Exam weight | 60% |
| Pass mark | 50 |
| Terms per year | 3 |
| Term label | Trimestre |

---

## National Examinations

| Exam | Subsystem | Level | Awarding body |
|------|-----------|-------|---------------|
| CEP (Certificat d'Études Primaires) | Francophone | CM2 | MINEDUB |
| BEPC (Brevet d'Études du Premier Cycle) | Francophone | 3ème | MINESEC / OBC |
| Probatoire | Francophone | Première | MINESEC / OBC |
| BAC | Francophone | Terminale | MINESEC / OBC |
| First School Leaving Certificate (FSLC) | Anglophone | Class 6 | MINEDUB |
| GCE Ordinary Level | Anglophone | Form 5 | GCE Board |
| GCE Advanced Level | Anglophone | Upper Sixth | GCE Board |

---

## HR & Statutory Deductions

| Deduction | Rate | Body |
|-----------|------|------|
| IRPP (Impôt sur le Revenu des Personnes Physiques) | Progressive bands | DGI |
| CNPS — Vieillesse (employee) | 2.8% | CNPS |
| CNPS — Vieillesse (employer) | 4.2% | CNPS |
| CNPS — Accident du travail (employer) | 1.75–5% (by sector) | CNPS |
| CNPS — Allocations familiales (employer) | 7% | CNPS |

---

## Notes

- XAF (CEMAC zone) is distinct from XOF (UEMOA zone), though both are pegged to the EUR at the same rate
- Cameroon operates on GMT+1 year-round — same timezone as Nigeria (WAT)
- The academic year typically runs September to June
- Bilingual deployments may require dual grading scale configurations (one for each subsystem)
