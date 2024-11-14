# Introduction

This lab is divided into two parts where you will evaluate and attack the security of an embedded device.

The lab can be developed in a team of up to 4 members (exceptions must be approved). See the lab submission dates in Moodle.

In your submission, describe the procedures you followed. Please explain noteworthy or unexpected observations. Don’t forget to address all the questions and targets in the lab description. Provide details on how you arrived at the conclusions/results (do not just paste the result). **All submissions must**:

1. Be in a ZIP file with the following format: `<student_id_1>_<student_id_2>..<student_id_n>.zip`.
2. Include all of the code used and relevant additional documentation (in any form that makes sense for you).
3. Have a `README.md` file that links and describes all information and files delivered. It should describe the relevant compilation/invocation for the relevant code used to extract information and the answer to **ALL** questions asked in the Lab description. **It must also include the Arduino identification number.**
4. A `TARGETS` folder must be present with a `secrets.csv` file that has a single line containing the following comma-separated information:
	1. Arduino ID;
	2. Dans' password;
	3. Alans' password;
	4. c&c password;
	5. Final secret.
5. All other target information must be present in the `TARGETS` folder.


## Criteria

The Lab will be graded using the following rubric. Please use this detailed rubric as guidance to create a good, detailed report. If the assignment is deemed unacceptable in a given criterion, a 0 will be given to that respective criterion.

Instructors will only help you with general hints and procedures to carry on your analysis. **At any point during the Lab, you can ask the instructor for hints specific to the solution. These requests must be performed by email, and will be considered during grading.**

|                                | **weight**       | **Exemplary**  **(100%)**                                    | **Accomplished**  **(75%)**                                  | **Satisfactory**   **(50%)**                                 | **Poor**  **(25%)**                                          |
| ------------------------------ | ---------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Organization and  Language** | 10%              | Good organization, easy  to follow and relate to the lab activities.  No major language  (Grammar, Usage, Mechanics, Spelling) errors. | Organized, but points  are somewhat jumpy or hard to follow.  Only one or two important  language errors. | Some organization; points  jump around; hard to follow.  More than two important  errors. | Poorly organized; no  logical progression; hard to connect with lab activities and logical flow.  Numerous errors  distract from understanding. |
| **Targets 1-7**                | 90%  (~13% each) | The target was provided  independently (little to no help specific to the solution) | The target was provided  somewhat independently (some help specific to the solution) | The target was provided,  but with a good amount help specific to the solution | Little to no independent  work toward the solution           |


## Arduino Hardware Issues

If you detect a problem with the Arduino assigned to you, please contact your instructor **as soon as possible to resolve the issue**.

# Insecure vending machine

Our company acquired a new vending machine for our High Tech building.
The machine has a service for automatic restocking, so it needs to be connected to the internet.
Due to the signed contract, this connection can't be taken down because it also allows the vending machine company to ensure the coherence between products bought and products available.

Since we cannot have a compromised machine with internet access near our high-tech projects, our cyber teams decided to start investigating that machine.

The investigation team has done some preliminary work, and you are tasked with exploiting the supposedly identified vulnerabilities.

# PART 1: Initial targets

## Development password
We saw the maintenance guy open a dev console. Let's see how secure the access to it is.
From our initial investigations, we believe input isn't being properly handled. Looks like password validation has different delays, depending on the input password.
Maybe we can try a **timing attack** to obtain as many credentials as possible.

**TARGET 1: Developer password**

How did you infer the password?
If you used a timing attack, plot the timing graphs for the first and second letters
If not, how long did it take to crack it?
>Hint:
>1. If you perform a timing attack, start by inferring length (length comparison is done before anything else)
>Due to *hardware constraints* you can assume that at most 20 characters are used, and only lowercase a-z characters
>2. If you don't find the right tool for the job and decide to create it yourself, make it abstract enough so further programming of the communication with the target is easy. Either way, you have the freedom to do as you want


## Firmware
We need to get the flashed firmware to do any analysis.
The development console may help with that.

**TARGET 2: The dumped firmware in a binary file**

## Confidential Information
While our reverse engineering team is investigating the firmware, we can already extract information. What information is there to extract?

**TARGET 3: Confidential strings**
>Hint:
>The first analysis of any firmware involves looking at the strings present to infer the possibly hardcoded assets and other information about the system. We need all relevant information, as well as why it is relevant.

