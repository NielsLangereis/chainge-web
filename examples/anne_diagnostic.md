# Diagnostic for Anne / Brabant Advanced Materials

What Chainge surfaced after ingesting the company profile (full JSON: [anne.json](anne.json)). The diagnostic is a single review pass over the structural exposure profile, before any cascade chain is generated. It is the gate between "profile received" and "cascades surface."

Snapshot: 2026-05-13.

---

Inferred persona: operator
Overall status:   needs_review

Regulatory note: Regulatory regime cross-check used model training-data knowledge of EU regulations (including CBAM Regulation (EU) 2023/956, CRMA Regulation (EU) 2024/1252, CSRD Directive 2022/2464, and REACH Regulation (EC) 1907/2006); live EUR-Lex primary-source lookup via CELLAR SPARQL is unavailable in this build. Treat regime tagging assessments — particularly the CBAM scope analysis and CRMA applicability — as informed but not authoritative. Verify against current EUR-Lex consolidated texts and, where material, with EU regulatory counsel before acting.

11 diagnostic item(s):

[1] WARNING on 'unknown_or_uncertain'
    Issue:    NdPr ore concentrate upstream provenance is unspecified. The profile acknowledges China-dominant sourcing but the exact supplier/refiner mix is unknown. This is cascade-critical: inland Chinese smelter regions (Inner Mongolia, Jiangxi, Sichuan) have materially different water-stress and energy-mix profiles, and geopolitical export-control risk (China's REE export licensing regime) varies by refiner tier.
    Resolve:  Request a supplier declaration identifying the named refiner(s) and mine origin (e.g., Bayan Obo / JLMAG / Shenghe Resources). If unavailable, default cascade assumption should be Inner Mongolia coal-mix smelter with high water-stress exposure. Flag for supply-chain due diligence under the forthcoming EU Critical Raw Materials Act (CRMA) traceability provisions.
    Requires user input.

[2] WARNING on 'unknown_or_uncertain'
    Issue:    Exposure to upstream Russian natural-gas pricing on EU ammonia and ethylene-glycol feedstocks is unquantified. Ammonia is highly gas-price-sensitive (gas is ~70–80% of production cost); ethylene glycol is also fossil-derived. If European suppliers are passing through TTF/NBP gas-cost volatility, the eSil and CoatPro line margins are indirectly exposed to Russian gas disruption cascades even without direct Russian sourcing.
    Resolve:  Ask each ammonia and ethylene-glycol supplier for their gas-cost passthrough clause structure (fixed vs. indexed). If indexed to TTF, model a ±30% TTF scenario on input cost. Consider whether a gas-price hedge or fixed-price supply contract is available. Add to cascade as an indirect energy-price pathway.
    Requires user input.

[3] INFO on 'unknown_or_uncertain'
    Issue:    Whether the eSil electronic-grade silane line falls under any CBAM scope extension for specialty chemicals (mooted for 2027) is flagged as uncertain. As of the current CBAM Regulation (EU) 2023/956, silane intermediates are not in scope. The European Commission's CBAM review clause (Article 30) requires a report by 2025 on potential scope extension, but no formal proposal has been tabled for specialty silanes.
    Resolve:  Monitor the Article 30 review report (expected H2 2025). No action required now; add a regulatory watch item. If scope extension is proposed, the Antwerp toll-finishing line (Belgium, EU) would not trigger CBAM as it is an intra-EU operation — CBAM applies at the EU external border, not between member states.

[4] WARNING on 'regulatory_regimes'
    Issue:    CBAM is tagged with an uncertainty flag. Under the current CBAM Regulation (EU) 2023/956, the covered sectors are: cement, iron and steel, aluminium, fertilisers, hydrogen, and electricity. Brabant Advanced Materials imports rare-earth oxide concentrates and silicon metal — neither of which is currently in CBAM scope. Silicon metal is not classified as 'aluminium' under CBAM CN codes, and rare-earth concentrates are not covered. The CBAM tag as currently applied is likely a false positive.
    Resolve:  Remove CBAM from regulatory_regimes as a direct compliance obligation. Retain a note in unknown_or_uncertain that (a) the Article 30 scope-extension review could bring specialty chemicals or silicon metal into scope post-2027, and (b) upstream CBAM cost pass-through from any steel or aluminium used in capital equipment or packaging is an indirect cascade pathway, not a direct liability. Confirm with your EU regulatory counsel.
    Requires user input.

[5] WARNING on 'regulatory_regimes'
    Issue:    The EU Critical Raw Materials Act (CRMA, Regulation (EU) 2024/1252, in force June 2024) is not tagged. Brabant Advanced Materials works directly with rare earths (lanthanum, cerium, neodymium, praseodymium) and silicon metal — all of which appear on the CRMA Strategic Raw Materials list. As a downstream processor supplying automotive electrification and semiconductor OEMs, the company sits in a supply chain that is subject to CRMA stress-testing and traceability obligations imposed on large OEM customers, which will cascade upstream via contractual due-diligence requirements.
    Resolve:  Add 'EU Critical Raw Materials Act (CRMA)' to regulatory_regimes. Immediate direct obligations are limited for an SME of this size, but OEM customers (especially automotive Tier 1s) will begin requiring CRMA-aligned supply-chain declarations. Engage with the European Critical Raw Materials Alliance (ERMA) and review CRMA Article 45 audit provisions.
    Requires user input.

[6] INFO on 'regulatory_regimes'
    Issue:    EU REACH is correctly tagged and highly material for this profile (high-purity specialty chemicals, silane intermediates, rare-earth compounds). However, REACH authorisation (Annex XIV) and restriction (Annex XVII) timelines for specific substances in the NdPr and eSil lines — particularly certain solvents and ion-exchange resin precursors — may require sunset-date tracking. This is not a tagging error but a cascade-depth note.
    Resolve:  Ensure REACH substance registration dossiers for lanthanum oxide, cerium oxide, and NdPr concentrate are current (post-2018 registration deadline). Verify that any Substances of Very High Concern (SVHCs) in the CoatPro organic binders or eSil solvents are tracked against the ECHA Candidate List. No regime change needed — this is a depth flag for the cascade.

[7] INFO on 'regulatory_regimes'
    Issue:    EU CSRD is tagged as applying from FY2026. At ~€45M revenue and ~95 staff, Brabant Advanced Materials is below the large-undertaking threshold (250+ employees OR €50M+ turnover AND €25M+ balance sheet) for the first wave (FY2024 reporting). However, if revenue exceeds €50M or staff exceeds 250 before FY2026, the threshold triggers. The FY2026 start date in the profile is plausible but should be confirmed against the exact threshold test.
    Resolve:  Confirm CSRD applicability date by running the dual-criterion test (employees AND/OR turnover + balance sheet) against FY2024 and FY2025 actuals. If the company remains below 250 employees and under €50M revenue, CSRD may apply from FY2026 only if the balance-sheet threshold is also met. SME voluntary standard (VSME) may be the more appropriate framework in the interim.
    Requires user input.

[8] INFO on 'input_categories'
    Issue:    Silicon metal is tagged under 'energy-intensive metals' — correct, as silicon metal smelting is highly electricity-intensive. However, the smelter region for the industrial-grade silicon metal input is not specified anywhere in the profile or unknown_or_uncertain. European silicon metal production is concentrated in Norway (Elkem, REC Silicon) and France (Ferroglobe); Chinese production (Yunnan, Sichuan) is also a major global source. The origin matters for energy-mix cascade (Norwegian hydro vs. Chinese coal) and for potential CBAM scope-extension exposure.
    Resolve:  Add silicon metal smelter/origin region to unknown_or_uncertain. If sourced from Norwegian or French producers, the energy-mix cascade is relatively clean. If sourced from Chinese spot markets, flag for geopolitical supply-chain risk and potential future CBAM exposure. Ask the eSil line procurement team for the named silicon metal supplier.

[9] INFO on 'input_categories'
    Issue:    Ammonia is listed as a key input for the eSil line and tagged under 'fossil-derived polymers and intermediates.' Ammonia is also a CBAM-covered product under the current regulation (CN codes 2814). If Brabant Advanced Materials imports ammonia from outside the EU, it may have a direct CBAM obligation for that specific input — distinct from the question of whether its own finished products are CBAM-covered.
    Resolve:  Clarify whether ammonia is sourced from EU producers (e.g., OCI, Yara — both EU-based) or imported directly from non-EU origins. If imported from non-EU, a CBAM declarant obligation applies for ammonia specifically. This is a narrow but real CBAM exposure that should be separated from the broader (incorrect) CBAM tag on finished products. Add to unknown_or_uncertain if sourcing origin is unclear.
    Requires user input.

[10] WARNING on 'currency_exposure'
    Issue:    CNY exposure on NdPr concentrate spot purchases is flagged as unhedged. Given that the NdPr line represents ~20% of revenue and rare-earth concentrate is its primary input, unhedged CNY exposure creates a structural margin risk that is asymmetric: CNY appreciation vs. EUR increases input costs with no natural offset (all revenue is EUR). Additionally, Chinese export licensing restrictions on REEs (as seen with the 2023 gallium/germanium controls and 2024 REE processing technology export restrictions) could cause spot price spikes denominated in CNY that compound the FX effect.
    Resolve:  Quantify the annual CNY-denominated spend on NdPr concentrate spot purchases. If material (>€1M equivalent), evaluate CNY/EUR forward cover or a natural hedge via EUR-invoiced long-term supply contracts with Chinese refiners. Flag for treasury review. Add CNY hedge status to unknown_or_uncertain.
    Requires user input.

[11] INFO on 'currency_exposure'
    Issue:    EUR/USD mismatch on rare-earth ore concentrate invoicing is correctly identified in notable_mismatch. The REC and NdPr lines together represent ~55% of revenue, and their primary feedstocks are USD-invoiced. This is a well-formed entry — no structural error — but the cascade should model a ±10% EUR/USD scenario on gross margin for those two lines specifically.
    Resolve:  No profile correction needed. Ensure the cascade model applies EUR/USD sensitivity to the REC (35%) and NdPr (20%) lines' input cost base. Confirm whether any USD hedging is in place (not mentioned in the profile).

---

*Profile confirmed; cascades now surface against this baseline.*
