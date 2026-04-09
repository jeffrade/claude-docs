# Bernstein v. National Institute of Standards and Technology
### A Legal Case Summary — *NSA, NIST, and Post-Quantum Cryptography*

> Compiled from 2,843 FOIA-produced documents at [nist.pqcrypto.org/foia](https://nist.pqcrypto.org/foia/index.html) and related external sources.

---

## Table of Contents

1. [Case Overview](#case-overview)
2. [Background](#background)
   - [NIST PQC Standardization](#nist-pqc-standardization)
   - [NSA's Documented History](#nsas-documented-history)
   - [Post-Dual-EC Reform Commitments](#post-dual-ec-reform-commitments)
3. [Core Legal Claims](#core-legal-claims)
4. [Key Evidence from FOIA Releases](#key-evidence)
   - [NSA Staffing](#nsa-staffing)
   - [NSA Coordination Meetings](#nsa-coordination-meetings)
   - [NSA Direct Input on Algorithm Selection](#nsa-direct-input)
   - [GCHQ Access Through NIST](#gchq-access)
   - [Hidden Documents](#hidden-documents)
   - [Patent Policy Suppression](#patent-policy-suppression)
   - [Ethics Violations](#ethics-violations)
5. [Procedural History](#procedural-history)
6. [Technical Allegations](#technical-allegations)
7. [Government's Position](#governments-position)
8. [Current Status and Outcome](#current-status)
9. [Source Limitations](#source-limitations)

---

## Case Overview {#case-overview}

Daniel J. Bernstein ("djb"), cryptographer and co-submitter of NTRU Prime to NIST's Post-Quantum Cryptography Standardization Process ("NISTPQC"), filed two federal FOIA lawsuits against the National Institute of Standards and Technology ("NIST"), an agency of the U.S. Department of Commerce. Bernstein is represented by **Loevy & Loevy**, a Chicago-based civil-rights litigation firm.

| | |
|---|---|
| **Case 1** | Docket 64872195 |
| **Case 2** | Docket 67850655 |
| **Court** | U.S. District Court (district uncertain: D.C. per djb's blog; N.D. Ill. per FOIA index) |
| **Plaintiff** | Daniel J. Bernstein |
| **Defendant** | National Institute of Standards and Technology / U.S. Dept. of Commerce |
| **Plaintiff's counsel** | Loevy & Loevy |

The first lawsuit was filed in 2022 after NIST returned **zero responsive records** to multiple FOIA requests spanning mid-2020 through March 2022. The second lawsuit was announced on August 5, 2022, when djb published his foundational blog post at [blog.cr.yp.to/20220805-nsa.html](https://blog.cr.yp.to/20220805-nsa.html).

The litigation has produced rolling document releases totaling **2,843 documents** across delivery batches from October 3, 2022 through November 25, 2025, catalogued at [nist.pqcrypto.org/foia/index.html](https://nist.pqcrypto.org/foia/index.html).

The government's litigation filings — motions, Vaughn indices, and court orders — were not accessible during research. CourtListener's docket returns 403 errors; MuckRock is similarly inaccessible to automated queries.

---

## Background {#background}

### NIST PQC Standardization {#nist-pqc-standardization}

In December 2016, NIST issued a Call for Proposals to solicit post-quantum cryptographic algorithms for standardization, promising an "open and transparent" process. Over the following six years, NIST evaluated 69 initial submissions through multiple elimination rounds, ultimately selecting four algorithms in July 2022:

- **CRYSTALS-Kyber** (key encapsulation, now ML-KEM / FIPS 203)
- **CRYSTALS-Dilithium** (digital signature, now ML-DSA / FIPS 204)
- **Falcon** (digital signature, now FN-DSA / FIPS 206)
- **SPHINCS+** (digital signature, now SLH-DSA)

Bernstein's NTRU Prime submission was not selected.

NIST's transparency commitment was emphatic and repeated:

> *"We operate transparently. We've shown all our work."*
> — Matthew Scholl, NIST, 2021

> *"We will continue to work in an open and transparent manner with the crypto community for PQC standards."*
> — Dustin Moody, PQCrypto 2019 (`20221014/pqcrypto-may2019-moody (1).pdf`)

---

### NSA's Documented History {#nsas-documented-history}

The relevance of NSA involvement cannot be evaluated in isolation. Bernstein's litigation invokes a documented pattern spanning decades ([blog.cr.yp.to/20220805-nsa.html](https://blog.cr.yp.to/20220805-nsa.html)):

#### DES (1977–2005)
The NSA pressured IBM to limit the Data Encryption Standard's key length to **56 bits**. NSA Director Bobby Inman denied tampering in 1979. The EFF broke DES for $250,000 in 1998. The weakened standard survived until 2005 — nearly 30 years.

#### DSA (1991)
The NSA secretly authored the Digital Signature Algorithm. A FOIA lawsuit by Computer Professionals for Social Responsibility disclosed NSA authorship. Initial 512-bit key parameters were inadequate; Ron Rivest warned of this in 1992. The 2010 Sony PlayStation breach exploited the exact ECDSA vulnerability Rivest had flagged.

#### Dual EC DRBG (2006–2013)
The NSA engineered a backdoor into the Dual Elliptic Curve Deterministic Random Bit Generator, standardized in NIST SP 800-90A. NSA reportedly paid RSA Security **$10 million** to make it the default generator. The *New York Times* confirmed the NSA's engineering role in 2013 based on Snowden disclosures, which revealed a $250 million/year **"Sigint Enabling Project"** with objectives including:

> *"Insert vulnerabilities into commercial encryption systems"*
>
> *"Influence policies, standards and specification for commercial public key technologies"*

---

### Post-Dual-EC Reform Commitments {#post-dual-ec-reform-commitments}

Following the Dual EC debacle, NIST's Visiting Committee on Advanced Technology (VCAT) issued a **2014 reform report** making explicit commitments:

> *"NIST may seek the advice of the NSA on cryptographic matters but it must be in a position to assess it and reject it when warranted."*

> *"All of NSA's contributions and authorship will be acknowledged in the relevant standard."*

The 2014 VCAT report also documented that the **1989 NIST/NSA MOU** gave NSA an effective veto over standards — requiring NIST to resolve any NSA objection before taking action. The 2010 MOU revised but did not eliminate pre-disclosure review requirements.

Whether NIST honored these reform commitments in the NISTPQC process is a central question in the litigation.

---

## Core Legal Claims {#core-legal-claims}

Bernstein's lawsuits assert claims under the **Freedom of Information Act, 5 U.S.C. § 552**:

**Wrongful withholding:** NIST returned zero responsive records to multiple FOIA requests filed between mid-2020 and June 2021 seeking NSA-NIST communications regarding PQC standardization. A March 2022 MuckRock request (#126349) also returned zero records. Subsequent FOIA litigation produced 2,843 documents — demonstrating the zero-records responses were incorrect.

**Inadequate search:** The sheer volume of documents ultimately produced suggests NIST's pre-litigation search methodology was deficient.

**Relief sought:** Production of all responsive non-exempt records; a Vaughn index identifying withheld records and applicable exemptions; attorney's fees and costs.

---

## Key Evidence from FOIA Releases {#key-evidence}

### NSA Staffing {#nsa-staffing}

`20230815/Re_ pqc mailing list(1)-3.pdf` — Email dated September 13, 2016, from Rene Peralta (NIST) to Dustin Moody (NIST).

The internal `pqc@nist.gov` mailing list had **23 members**, of which Bernstein identifies **11 as NSA personnel**:

| Name | Notes |
|------|-------|
| Scott Simon | NSA |
| Nick Gajcowski | NSA |
| Mark Motley | NSA |
| Laurie Law | NSA |
| John McVey | NSA |
| Jerry Solinas | NSA; publicly known NSA cryptographer; *"reportedly heading NSA's post-quantum efforts since 2004"* |
| Daniel Kirkwood | NSA |
| David Tuller | NSA |
| David Hubbard | NSA; *"currently Director of Legislative Affairs"* |
| Bradley C. Lackey | NSA |
| **Rich Davis** | NSA; email **`radavi1@nsa.gov`** — explicitly added by Moody (`20230815/Re_ pqc mailing list-2.pdf`) |

Additional members included Jacob Farinholt (Naval Surface Warfare Center / Booz Allen Hamilton), Jonathan Katz and Bill Fefferman (QuICS, UMD-NIST partnership), and confirmed NIST employees.

**This directly contradicts the March 2014 ISPAB presentation** (`a_quantum_world_v1_ispab_march_2014.pdf`), which attributed the entire project to *"Post Quantum Cryptography Team, NIST, pqc@nist.gov"* and listed **only 7 NIST employees, zero NSA members** — a presentation made while NIST was simultaneously promising in VCAT proceedings to disclose all NSA authorship.

Similarly, Rene Peralta's **NUTMIC 2017 slides** (`20250114/NUTMIC copy.pdf`) publicly acknowledged the community's *"suspicion that NIST is just doing NSA's bidding"* and rebutted it by pointing only to the NIST team roster — while omitting the NSA members entirely.

---

### NSA Coordination Meetings {#nsa-coordination-meetings}

Multiple produced documents establish a pattern of pre-announcement NSA consultation:

**`20230619/Re_ PQC meeting tomorrow(1).pdf`** — Liu quoting Moody, January 12–13, 2016:

> *"I appreciated the feedback from the NSA and Donna, as they gave us a perspective I think we were lacking."*

> *"Andy told me the NSA wants to coordinate with us before PQCrypto, so they know what we are going to say. Sounds reasonable. I don't think we've told our **NSA friends** what our plans are?"*

**`20230315/Outline for PQC announcement.pdf`** — Internal CFP planning outline, January 14, 2016:

> *"Contact info (pqc@nist.gov – **NSA gets this email as well. Need new email?**)"*

No separate email was ever created. All public submissions routed to NSA.

**`20230508/pqc stuff.pdf`** — Moody, January 21, 2016:

> *"Our next meeting with the NSA, we'll also tell them of our plans… We can also share with them our NISTIR."*

> *"Feb 2nd, we have Michael Groves from the CESG in UK coming… He'll share with us some stuff ETSI has going on."*

CESG is the cryptographic standards branch of GCHQ, NSA's UK partner.

**`20230619/Slides for our Crypto Club talk.pdf`** — Moody, January 27, 2016:

> *"We were going to meet with the NSA yesterday, but NIST was closed. The NSA still wants to meet with us soon for us to give them an update on what we will be saying at PQCrypto."*

---

### NSA Direct Input on Algorithm Selection {#nsa-direct-input}

**`20241115/pqc round 2 report.pdf-attachment`** — June 2020 draft of NIST's Round 2 Report.

NSA's **Morgan Stern** provided comments embedded within Moody's name as tracked Word document comments. Stern directed:

> *"Start the paragraph with something like: **In a technical sense, the security of NewHope is never better than that of KYBER.**"*

This text appeared **verbatim in the final published NIST Round 2 Report**.

Stern also directed regarding NTRU:

> *"I think you need to come out and tell them to make a level 5 parameter set under their non-local model."*

**`20241213/NSA-PQC comments (1-16-2018).docx`** — NSA memo to NIST, January 2018:

NSA praised lattice-based cryptography as *"well-studied cryptographic primitives"* with *"a long history of analysis"* and recommended **"low priority"** for schemes based on *"particularly exotic or niche areas of mathematics"* — functionally targeting NTRU Prime's non-cyclotomic ring design.

**`20240318/Re_ PQC CFP_1.pdf`** — Moody to Liu, May 2016:

> *"Here's what you 'volunteered' to take a look at: The **NSA's comment on section 2.B.1 paragraph 3.**"*

NSA had direct editorial input on the competition's governing rules.

**NIST's public denial** (`20221014/pqcrypto-sept2020-moody.pdf`, Sep 2020 conference):

> *"The feedback received (from the NSA) did not change any of our decisions and did not substantively change our 2nd Round Report."*
> *"NIST alone makes the PQC standardization decisions, based on publicly available information."*

This is directly contradicted by Stern's text appearing verbatim in the final report.

---

### GCHQ Access Through NIST {#gchq-access}

**`20231110/FW_ Our Feb 2nd PQC meeting with Michael Groves.pdf`** — Perlner forwarding to Regenscheid, January 27, 2016. Marked: *"Note, these documents are for internal use only — not to be shared."*

GCHQ's Michael Groves visited NIST with pre-publication ETSI documents and wrote:

> *"Could you note that these documents are still in preparation and formally owned by ETSI. In particular you should not show them to anyone outside your immediate **NIST (and IAD) colleagues** until the final versions are made public."*

**IAD = NSA's Information Assurance Directorate.** Groves knew and explicitly accepted that NSA would see the restricted ETSI documents. The general public and competing cryptographers would not.

---

### Hidden Documents {#hidden-documents}

**24 documents confirmed as marked "Not for public distribution," "For internal use only," or equivalent** — produced only through FOIA litigation:

| Document | Marking |
|----------|---------|
| `20221014/PQC Seminar 6-1-18.pdf` | *"Not for public distribution"* |
| `20221014/PQC Seminar 7-13-18 (BIG QUAKE).pdf` | *"Not for public distribution"* |
| `20221014/PQC Seminar 8-14-18 (Lizard).pdf` | *"Not for public distribution"* |
| `20221014/PQC Seminar 10-19-18 (QC-LDPC schemes).pdf` | *"Not for public distribution"* |
| `20221014/PQC Seminar 5-21-19 (Frodo-KEM).pdf` | *"Not for public distribution"* |
| `20221014/PQC Seminar 7-23-19 (ThreeBears).pdf` | *"Not for public distribution"* |
| `20221014/PQC Seminar 2-11-20 (Fiat-Shamir).pdf` | *"Not for public distribution"* |
| `20221014/PQC Seminar 9-14-21 (Dilithium and Falcon).pdf` | *"Not for public distribution"* |
| `20221014/PQC Seminar 11-12-21 (Classic McEliece).pdf` | *"Not for public distribution"* |
| `20221014/NIST Crypto Short Talk 8-13-21.pdf` | *"For internal use only – not for public distribution"* |
| `20221213/Performance of Rainbow Quynh.pptx` | *"For internal use only"* |
| `20221213/Performance of Gemss Quynh.pptx` | *"For internal use only"* |
| `20230118/NTRUPrime-2021-November.pdf` | *"Not for distribution"* |
| `20230118/SIKE-2021-November.pdf` | *"Not for distribution"* |
| `20230118/Updated Presentation on KYBER & SABER… (3).pptx` | *"KYBER & SABER: UPDATED REVIEW FOR 3RD ROUND (FOR INTERNAL USE ONLY)"* |
| `20230105/Dillithium_Falcon-finalish.pptx` | *"Only for internal use"* |
| `20221213/Rainbow.pptx` | *"For internal use only… unlike a hairdryer."* |
| `20221213/GeMSS.pptx` | *"For internal use only… unlike a hairdryer."* |
| *(+ 6 additional PQC Seminar series documents)* | *"Not for public distribution"* |

**`20230105/Dillithium_Falcon-finalish.pptx`** is particularly significant: this is NIST's **final comparative analysis of the two signature finalists**, completed **eight months before** the July 2022 public selection announcement, and marked "Only for internal use." It contains an arithmetic labeling error in the central TLS sizing comparison, annotates Falcon's superior performance with rainbow emojis, and records an unresolved security concern about Dilithium.

**`20230105/lattice-overview-3.1.2021.pptx`** — labeled "NIST internal talk": NIST built its own internal cryptanalytic capacity against Kyber-512, with uncertain results, and references a **private SharePoint repository of evaluation discussion notes** that has not been produced in the FOIA litigation.

djb annotates each hidden document with: *"What happened to 'open and transparent'?"*

---

### Patent Policy Suppression {#patent-policy-suppression}

A four-draft internal patent policy process was never published.

**`20230517/Third Draft NIST ITL Patent Process for Its P.docx`** (February 6, 2015) — Hard exclusion rule:

> *"If the patent claim appears to be pertinent to NIST, **the publication shall not include provisions depending on that patent.**"*

**`20230517/Fourth Draft NIST ITL Patent Process for Its .docx`** (March 13, 2015) — Substantively identical; hard exclusion rule unchanged.

**`20231219/FW_ IPR for PQC Call For Submissions_1.pdf`** (March 2016): Moody workshopped IPR language privately, comparing it to SHA-3's royalty-free requirement.

**`20251125/Re_ IPR issue on PQC.pdf`** (October 20–24, 2016) — **The IPR capitulation:**

An unnamed internal figure ("Ajit," reporting to Gordon Gillerman) successfully prevented return to royalty-free requirements. Lily Chen to Regenscheid:

> *"We do not have a convincing reason to tell people why we moved away from IPR free requirements."*

The resolution: add "preference" language rather than require royalty-free — enabling Kyber's selection despite **7+ patent families**. The NIST patent license did not activate until 2024.

Public commenters including Mozilla explicitly objected to the departure from SHA-3's royalty-free standard during the August 2016 Federal Register comment period. Their objections were not addressed.

---

### Ethics Violations {#ethics-violations}

**Algorithm renaming:**

`20230118/NTRUPrime-2021-November.pdf` (marked "Not for distribution"): NIST classified Bernstein's **sNTRUPrime as "Quotient LWE"** — a taxonomy suppressing the algorithm's distinct design innovation of non-cyclotomic rings, which Bernstein had identified as a security advantage. The same taxonomy was propagated externally at the Dagstuhl Seminar (`20221003/Dagstuhl Slides.pptx`).

Same document lists as an official comment in the public record:

> *"D. Bernstein: Complaint that NIST has been discouraging public discussion of patent issues."*

**Kyber patent risks hidden:**

`20230118/NTRUPrime-2021-November.pdf` explicitly tables Kyber patent risks (patents 9094189 and 9246675) in internal slides. These risks were never disclosed in NIST's public evaluation reports.

Same document notes: *"If we standardize Kyber or Saber, we should address these criticisms in our report"* — no public report doing so was produced.

**Retroactive criteria application:**

NIST internally demanded Level 5 parameter sets from remaining submissions, documented internally with the word *"now"* acknowledging it was a new requirement, then framed publicly as always-expected.

---

## Procedural History {#procedural-history}

| Date | Event |
|------|-------|
| Mid-2020 – Jun 2021 | Multiple FOIA requests for NSA-NIST PQC communications → **zero records** each |
| March 2022 | Comprehensive FOIA request via MuckRock (#126349) → **zero records** |
| 2022 | **First federal lawsuit filed** (Docket 64872195) |
| August 5, 2022 | **Second lawsuit filed** (Docket 67850655); djb publishes blog post |
| October 3, 2022 | First document production batch |
| Oct 2022 – Nov 2025 | Rolling productions: **2,843 documents** across 12+ delivery batches |

The transition from zero records to 2,843 documents is the most basic factual finding of the litigation: **NIST's pre-litigation search was manifestly inadequate.**

---

## Technical Allegations {#technical-allegations}

### CECPQ2 Factual Error

`20230105/KSN Document.docx` — Moody's internal "Kyber, Saber, and NTRU – Oh my!" scorecard (October 2021) listed Kyber as used in the Google-Cloudflare "CEPQ2" experiment. In fact, **CECPQ2 used NTRU (ntruhrss701) and SIKE**, not Kyber. This error appeared in the internal document driving the final KEM selection.

### Security Margin Uncertainty at Standardization

`20230105/KSN Comparison.pptx`:

> *"Kyber512 admits uncertainty of about 2^16, which could take it below our 2^143 threshold."*

> *"At this moment it is simply impossible to provide a definite and precise answer to this question [re: LightSaber's Category 1 classification]."*

`20221003/Dagstuhl Slides.pptx` — open question, unresolved:

> *"Is there security benefit to less structured lattice?"* (re: Kyber's module-LWE vs. ring-LWE alternatives)

`20230105/Dillithium_Falcon-finalish.pptx`:

> *"Security concern for latter on? ..could be? (speculation)"* — re: Dilithium

### Unquantified Evaluation Criteria

`20221213/PQ-signature-compare-presentation.pptx` (Kelsey, March 2020): Performance evaluation of all signature candidates **never established numeric pass/fail thresholds**. Rainbow was recommended for *"immediate standardization"* despite Kelsey identifying certificate-chain problems. **Rainbow was catastrophically broken in 2022** within hours on a laptop.

`20230105/Crypto in PQ world -DoC.pdf` (Moody/Chen, public DoC presentation): Performance comparisons use an **80-bit security baseline**, inconsistent with the competition's 128-bit minimum.

### Arithmetic Error in Final Selection Document

`20230105/Dillithium_Falcon-finalish.pptx`:

- Slide 34 formula: `6 × 2420 + 2 × 1312 = 17,144` ✓
- Slide 35 formula: `3 × 66 + 3 × 2420 + 2 × 1312 = 10,082` — but is **labeled "= 17,144"** before an arrow to the correct answer

The document annotates **Falcon's superior TLS footprint (3,990 vs 10,082 bytes) with rainbow emojis**. Dilithium was selected as the primary signature standard. The basis for reversing the internal preference is not documented in any public record.

### Internal Preferences Contradicted Final Selections

`20250416/Re_ My current point of view on standardization....pdf` — Apon to Moody, September 28–30, 2021:

> *"Currently, I lean 55/45 towards picking **Falcon** over Dilithium."* → **Dilithium selected primary.**

> *"There is no world in which I believe Saber should be standardized."* → Saber eliminated only because Kyber was selected, not on separate technical grounds.

> *"Obviously SIKE should be standardized at some point."* → **SIKE broken classically in 2022.**

### Post-Selection Algorithm Breaks

| Algorithm | Internal Status | Outcome |
|-----------|----------------|---------|
| Rainbow | Recommended for "immediate standardization" (Kelsey, 2020) | Broken in 2022 by classical attack |
| SIKE | Endorsed by NIST's Apon (Sept 2021) | Broken in 2022 by classical attack |

---

## Government's Position {#governments-position}

NIST's public defense is partially reconstructable from produced documents.

**`20221014/pqcrypto-sept2020-moody.pdf`** (September 2020 conference):

> *"The feedback received (from the NSA) did not change any of our decisions and did not substantively change our 2nd Round Report."*

> *"NIST alone makes the PQC standardization decisions, based on publicly available information, and stands by those decisions."*

> *"NIST encouraged the NSA to provide comments publicly."* (NSA declined.)

**VCAT 2014 reform posture:** NIST committed to requiring acknowledgment of all NSA authorship and to being able to "assess and reject" NSA advice independently.

> ⚠️ **The government's actual litigation defense is unknown.** No motions to dismiss, Vaughn indices, declarations, or court orders are in the accessible record. CourtListener returns 403 errors. The legal strength of any exemption claims cannot be assessed from available materials. Any full evaluation of the litigation's merits must be qualified by this absence.

---

## Current Status and Outcome {#current-status}

As of the most recent document production (November 25, 2025), the litigation has compelled the release of **2,843 documents** establishing:

- NSA personnel constituted a near-majority of the internal `pqc@nist.gov` mailing list while being **omitted from all public team rosters**
- NSA-authored text (**Morgan Stern's comment**) appeared verbatim in NIST's published Round 2 Report while NIST publicly denied substantive NSA influence
- At least **24 internal evaluation documents** were marked not for public distribution — including the final comparative analysis of signature finalists
- NIST's patent policy underwent an **internal reversal** from royalty-free requirements to RAND-permissive language, against public comment objections, with no convincing public rationale ("we do not have a convincing reason to tell people")
- Technical evaluation documents contain **factual errors**, arithmetic mistakes, and unresolved security questions that never surfaced in public reports

**What remains unknown:** Whether any court orders drove specific productions; whether additional documents remain withheld under FOIA exemptions; whether the cases are resolved, pending, or settled.

---

## Source Limitations {#source-limitations}

This summary is constructed primarily from documents produced in the FOIA litigation and catalogued at [nist.pqcrypto.org/foia/index.html](https://nist.pqcrypto.org/foia/index.html), supplemented by djb's August 5, 2022 blog post and public NIST statements. Several significant limitations apply:

**Plaintiff's framing predominates.** All document annotations, the organizational taxonomy of the FOIA index, and the interpretive framework are Bernstein's. The government's adversarial submissions — motions, declarations, Vaughn indices, memoranda of law — are not in the accessible record.

**Adjudicated facts vs. policy claims.** The documentary contents — who was on the mailing list, what text appeared in drafts, what documents were marked internal — are factual matters established by the produced records themselves. The interpretive claims — that NSA involvement corrupted the outcome, that Kyber was improperly favored, that NTRU Prime was improperly excluded — are Bernstein's advocacy, not adjudicated findings.

**No judicial rulings available.** No opinions, orders, or findings from either case are accessible. It is unknown whether any court has ruled on the adequacy of NIST's search, the propriety of any withholdings, or the merits of any exemption claims.

**Historical pattern evidence.** The DES, DSA, and Dual EC DRBG history cited in the Background section is drawn from djb's blog post and publicly reported facts. While well-documented, their legal relevance to FOIA claims — which concern the adequacy of document production, not the substantive merits of algorithm selection — is a matter of advocacy rather than adjudication.

**MuckRock inaccessible.** Both MuckRock FOIA request pages (requests #126349 and #138831) return 403 errors to automated access. Detailed government response timelines and communications logs for the two FOIA requests were not retrieved.

---

*All document citations reference the FOIA production date and filename as catalogued at [nist.pqcrypto.org/foia/index.html](https://nist.pqcrypto.org/foia/index.html). This summary does not constitute legal advice and does not represent the views of any party to the litigation.*
