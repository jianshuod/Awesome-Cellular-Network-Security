<div align="center">
    <h1>Awesome Cellular Network Security</h1>
    <a href="https://awesome.re"><img src="https://awesome.re/badge.svg"/></a>
</div>

A curated list of papers concerning Cellular Network Security

# Papers

## Formal verification
**[✔️] Instructions Unclear: Undefined Behaviour in Cellular Network Specifications**  \
*Daniel Klischies; Moritz Schloegel and Tobias Scharnowski; Mikhail Bogodukhov; David Rupprecht; Veelasha Moonsamy* (Ruhr University Bochum, CISPA Helmholtz Center for Information Security, Radix Security) \
the Proceedings of the 32nd USENIX Security Symposium (USENIX Security), 2023 [[Paper](https://www.usenix.org/system/files/usenixsecurity23-klischies.pdf), [Code](https://zenodo.org/records/8013704)] \
**Targets:** Public Warning System (PWS), SMS in LTE, RRC (3GPP. TS 36.331, release 14) \
**Tags:** L4 (undefined behaviors) \
**Main procedures:**
(1) Model the *defined* behaviour of the specification in *Temporal Logic of Actions* (Human effort)
(2) Detect *undefined* behaviours (extend this model via simple syntactic rules)
(3) Synthesize concrete PDU sequences that trigger undefined behaviour (to craft test cases) \
**Proof of Concept:** \
**Limitations:** 


## Fuzzing
**[✔️] Touching the Untouchables: Dynamic Security Analysis of the LTE Control Plane**  \
*Hongil Kim, Jiho Lee, Eunkyu Lee, Yongdae Kim* (KAIST) \
2019 IEEE Symposium on Security and Privacy (SP), 2019 [[paper](https://www.computer.org/csdl/proceedings-article/sp/2019/666000b153), [Slides](https://www.ieee-security.org/TC/SP2019/SP19-Slides-pdfs/Hongil_Kim_13_-_Touching_the_Untouchables.pdf)] \
**Targets:** NAS (3GPP. TS 24.301, version not exposed), RRC (3GPP. TS 36.331, version not exposed) \
**Tags:** Layer 2/4; Mutated-based black-box fuzzing; Control plane \
**Proof of Concept:** Verification of crafted test cases, attack setup\
**Limitations:** 
In other words, multi-stage vulnerabilities are currently beyond the scope of LTEFuzz. To diagnose multistage attacks, the tester first transitions to the target state by relaying the valid control plane messages between the UE and the network. When it reaches the target state, it may send unwanted messages. Cases such as these were previously demonstrated. The number of possible states as well as decision tree construction for all possible combinations of states seems to be the most significant challenge for stateful fuzzing.


## NLP
**[❌]**