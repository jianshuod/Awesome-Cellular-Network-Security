- **Touching the Untouchables: Dynamic Security Analysis of the LTE Control Plane**  \
*Hongil Kim, Jiho Lee, Eunkyu Lee, Yongdae Kim* (KAIST) \
2019 IEEE Symposium on Security and Privacy (SP), 2019 [[paper](https://www.computer.org/csdl/proceedings-article/sp/2019/666000b153), [Slides](https://www.ieee-security.org/TC/SP2019/SP19-Slides-pdfs/Hongil_Kim_13_-_Touching_the_Untouchables.pdf)] \
**Specs:** NAS (3GPP. TS 24.301, version not exposed), RRC (3GPP. TS 36.331, version not exposed) \
**Tags:** Layer 2/3; Mutated-based black-box fuzzing; Control plane \
**Proof of Concept:** Verification of crafted test cases, attack setup\
**Private id:** [24042701] \
**Limitations:** 
In other words, multi-stage vulnerabilities8 are currently beyond the scope of LTEFuzz. To diagnose multistage attacks, the tester first transitions to the target state by relaying the valid control plane messages between the UE and the network. When it reaches the target state, it may send unwanted messages. Cases such as these were previously demonstrated [5], [20]. The number of possible states as well as decision tree construction for all possible combinations of states seems to be the most significant challenge for stateful fuzzing.