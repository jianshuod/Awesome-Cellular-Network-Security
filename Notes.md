<div align="center">
    <h1>Awesome Cellular Network Security</h1>
    <a href="https://awesome.re"><img src="https://awesome.re/badge.svg"/></a>
</div>

A curated list of papers concerning Cellular Network Security

# Concept description
## Vulnerabilities of 6 levels
**Layer 1: Implementation errors.** They are the crashes or memory leaks resulting from incorrect programming behaviors.

**Layer 2: Incorrect conformance to the requirements.** The operators / vendors may fail to follow the standards or omit some steps.

---

**Layer 3: Ignoring the implementation feasibility.** The designs defined in the specs are logically feasible but practically challenging. For instance, a CPU needs time to finish one state transition. A vulnerable time window comes.

**Layer 4: Undefined Behaviors.** The ensuing complexity and lack of explicitness lead to underspecification, where only subsets of possible interactions are properly specified, while other behaviour is left undefined and open to interpretation by developers. (Negative testing)

**Layer 5：Design errors.** Some designs defined in the specs cannot form a compact and full-fledged operating mechanism to tackle a practical problem.
- Back compatability is not guaranteed.

**Layer 6: Root function errors.** The function of one single protocol cannot apply to actual environments.
- Some security properties are missing, leaving backdoors for malicious attackers.
- It fails to cooperate with other protocols, e.g., cross-protocol / cross-layer.
- New requirements (especially, from upper layers) make the protocol an old guy.
- undefined behaviors in cross-layer cases

## Methods to discover holes
**Stactic analysis:** Reading the specs and do logical games
- NLP
- Formal analysis

**Dynamic analysis:** Interacting with the target in a trial-and-error fashion
- Fuzzing

## Motivations to discover bugs
**Malicious intents:**

**Users:**

**Network operators:**

**Device vendors:**
- conformance test

**Pure research:** no need to make up a story

## Threat models
### Attack goals
#### Availability

**BTS resource depletion attack:** Every commercial eNB has a maximum capacity of active user connections based on their hardware and software specifications. The purpose of the BTS resource depletion attack is to deplete this capacity of the active RRC Connections, thereby preventing other users from connecting to the target eNB.

**Blind DoS attack**: blocking the service of one target UE
- Potential causes:
  - Make the context of victim UE deleted (disconnected and forced to reconnected: several seconds of service disconnection)

**Remote de-registration attack:** cause the MMEs to unnecessarily de-register the victim UE without notification

#### Confidentiality

**SMS phishing attack**

Identity Mapping Attack
- [layer2attack]
  
Replay attack

silent Paging attack:
- to obtain the S-TMSI of the victim

Website Fingerprinting attack
- [layer2attack]

Padding Oracle Attack:
- related to the integrity protection


#### Integrity

Spoofing

**AKA BYPASS ATTACK**: rogue LTE network does not negotiate the security algorithm for the RRC layer and user data in response to a connection request from the victim UE.

**DNS redirection attack**
- [layer2attack]


### Attack capacities

### Attack knowledge

**Passive attack:** The passive attacker eavesdrops transmis- sions in up- and downlink direction within the same cell the user is located in. Therefore, the attacker can receive and decode signals sent out by the eNodeB and the UE. To do so, it is not mandatory to have any knowledge about the established key material.

**Active Attacker.** In addition to the scope of the passive attacker, the active attack includes capabilities for sending radio signals on certain frequencies. Using these capabilities, the attacker can establish a malicious relay in the network by impersonating a UE towards the network and an eNodeB towards the user. Again, no knowledge of the key material is required for our attacks.

# Tools
## Open-sourced protocol stacks
[**srsLTE**](https://github.com/srsran/srsRAN_4G):
- used in [24042701]

[**OpenAirInterface (OAI)**](https://openairinterface.org/):
- used in [24042701]

[**openLTE**](http://openlte.sourceforge.net): 
- used in [24042701]

## Logging tools
[**SCAT**](https://github.com/fgsect/scat): 
- used in [24042701]

## Hardwares
**USPR B210**: software radio transceiver
- used in [24042701]

## Monitors
**Airscope**: provides over-the-air user information by decoding the communication channels in the physical layer of LTE

## Formal Verification

**$\text{TLA}^*$**: Introduction to TLA. Technical report.
- used in [24042901]

## Commands
**AT**: to refresh the chipset state (not sure)
- used in [24042701]


# Notes
1. ``Ethical considerations'' matter.
2. The relationship between the victim and the malicious:
  - in the same cell
  - in different cells but the same eNB
  - in different eNBs but the same MME pool 
3. To know about the victim's S-TMSI in three ways:
  - An adversary who has knowledge of the victim’s phone number or accounts on social media (such as Facebook and Whatsapp) could obtain the victim’s S-TMSI by performing a silent Paging attack [1], [2]. 
  - An adversary located in the vicinity of the target user could operate a rogue eNB to obtain the NAS TAU request of the victim UE. This request contains the S-TMSI of the victim UE. As soon as this message is received, the adversary turns off the rogue eNB to enable the victim UE to recover the LTE service by connecting to a carrier network. 
  - The adversary sniffs the RRC Connection procedure of the target UE to obtain the S-TMSI of the target UE as specified in the RRC Connection setup.
4. To obtain a control plane message of the victim UE
  - An adversary could operate a rogue LTE network to capture the control plane messages of the victim UE while relaying these messages between the UE and the network [4], [5]. 
  - An adversary could install a malicious app with control plane message logging functionality [29] on the UE.
5. An interview with a counterpart in the carrier revealed that an eNB might communicate with any MMEs regardless of the geographical regions and that this depended on the operational policy of the particular carrier.
6. A valid TA Code (TAC) can easily be captured in two ways:
  - If the adversary is subscribed to the same carrier as the victim, the list of TAs can be obtained by checking control plane messages such as Attach Accept. 
  - If the adversary only owns a rogue LTE network, she first chooses a TA randomly. Once the target UE connects to the rogue LTE network, it sends a TAU request as the TA of the connecting network is not on its list of TAs. Upon receiving the TAU request from the UE, the adversary can obtain the previous TAC of the UE by parsing the request. Note that the TAU request is only integrity protected.

### To be read
[1] Practical Attacks Against Privacy and Availability in 4G/LTE Mobile Communication Systems \
[2] Location leaks on the GSM Air Interface \
[3] LTEInspector: A Systematic Approach for Adversarial Testing of 4G LTE \
[4] Breaking LTE on Layer Two \
[5] Bookworm Game: Automatic Discovery of LTE Vulnerabilities Through Documentation Analysis. \
[6] ProChecker: An Automated Security and Privacy Analysis Framework for 4G LTE Protocol Implementations \
[7] Basespec: Comparative analysis of baseband software and cellular specifications for L3 protocols. \
[8] DoLTEst: Indepth Downlink Negative Testing Framework for LTE Devices \
[9] Insecurity of Voice Solution VoLTE in LTE Mobile Networks \
[10] GUTI Reallocation Demystified: Cellular Location Tracking with Changing Temporary Identifier. \
[11] Privacy Attacks to the 4G and 5G Cellular Paging Protocols using Side Channel Information \
[12] 5GReasoner: A Property-Directed Security and Privacy Analysis Framework for 5G Cellular Network Protocol \
[13] LTrack: Stealthy Tracking of Mobile Phones in LTE. \
[14] A Stealthy Location Identification Attack Exploiting Carrier Aggregation in Cellular Networks
[15] Control-Plane Protocol Interactions in Cellular Networks
[16] Formal Analysis of Access Control Mechanism of 5G Core Network

# Concepts should be in mind
PDU \
UE: User Equipment \
MNO: Mobile Network Operator \
eNB: eNodeB \
EPC: Evolved Packet Core \
PWS: Public Warning System \
SMS: Short Message Service \
RRC: Radio Resource Control \
DoS: Denial of Service \
PDU: Protocol Data Unit \
3GPP: 3rd Generation Partnership Project \
TLA: Temporal Logic of Actions
