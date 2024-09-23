# Ingles con fines generales y académicos IV

## Panel discussion (OREO)

In the panel discussion, we reached a conclusion with which everyone agreed: "money does not buy happiness". This topic has been widely debated throughout history, yet we still lack a definition that satisfies everyone, emphasizing the importance of recognizing that it is all a matter of perception.

Through the scientific method, we have found a way to approach the truth more closely. The article shared by the professor showed how they attempted to quantify happiness in the questionnaire used for statistical analysis. However, is this approach correct? Could we be limiting the investigation by formulating the questions in a certain way? The only certainty is that there is still much to unravel about this mystery, if we ever do.

Despite efforts to understand and measure happiness from a scientific perspective, we continue to face significant challenges. The complexity of the human being and their emotional experience makes happiness a multifaceted and ever-evolving topic. Furthermore, cultural, social, and personal variables significantly influence how we perceive and experience happiness. Therefore, it is crucial to understand that "definitive" answers (or at least somewhat more solid ones) may result from a continuous process of learning and reflection.

## Article review (A comparative study on shells in Linux)

The authors Abdullah Kidwai, Chandrakala Arya, Prabhishek Singh, Manoj Diwakar, Shilpi Singh, Kanika Sharma, Neeraj Kumar with their article "A comparative study in shells on Linux: A review" aimed to find the "best" shell on Linux by comparing general, interactive, programming and security features. Such features make a shell suitable for both a user and a developer. The authors expect the reader to have some basic knowledge of Linux and scripting.

The authors make clear the inevitable relationship that shells have with the world of Linux (mainly its philosophy of being open source), which caused that today there are numerous shells. For the users that enter this ecosystem it will be difficult to choose one, for this reason the article will make a comparison of the 7 most popular shells (Bourne Shell, C Shell, KornShell, Bash Shell, Z shell, Tcsh shell, and Fish shell) in characteristics that interest both a user and a developer, these characteristics are:

|         general         |    interactive features     |    programming     |            security            |
|:-----------------------:|:---------------------------:|:------------------:|:------------------------------:|
|       Invocation        |     Command completion      |     Functions      |     Secure password prompt     |
|   Default login shell   | Command argument completion | Exception handling | Encrypted variables/parameters |
| Default Scripting Shell |     Wildcard completion     |     Arithmetic     |   Untrusted script blocking    |
|     Unicode support     |    Automatic suggestions    |   Floating point   |    Restricted shell subset     |

The comparative analysis highlights the Z shell as the best option among the shells studied, based on its performance across various criteria. It concludes that Z shell stands out for its compatibility with existing scripts, modern features, and robustness. Result obtained by a valid criterion for these types of tools, although in the technology domain, especially within the Linux ecosystem, tools and frameworks can evolve rapidly, potentially affecting the relevance and applicability of comparative studies over time. It is important for readers to keep the temporal context in mind when evaluating the conclusions and recommendations of these types of studies.

## Academic poster (Open Sorce Software challenges: XZ Utils package case)

First, we need to define what is OSS, "it is code that is designed to be publicly accessible—anyone can see, modify, and distribute the code as they see fit"[what is open source from RedHat](https://www.redhat.com/en/topics/open-source/what-is-open-source), this leads to a decentralized and collaborative way of developing software. The most representative "product" is Linux, a system kernel originally written in $1991$ by Linus Torvalds. Linux is widely used in the technology field, developers and hosting services use distributions based on this open source kernel; specifically, specifically $96.3\%$ of the top over $1,000,000$ web servers use Linux[Linux usage statistics](https://www.enterpriseappstoday.com/stats/linux-statistics.html).

XZ Utils is a widely distributed set of open-source packages used for lossless data compression on Unix-like operating systems, including Linux. The vulnerability associated with it is CVE-2024-3094, and we can identify the following stages in the critical attack path:

1. Building trust.

    1. In $2021$, a user under the pseudonym "Jia Tan" began contributing regularly to the XZ Utils project.

    2. In $2022$, he was promoted and started having a more significant role in the project.

2. Preparation.

    1. In March $2023$, Jia Tan changed the primary contact in the Google OSS-Fuzz testing infrastructure to his own email.

    2. Introduction of the GNU IFUNC function, crucial for the hook mechanism used by the backdoor code.

3. Backdoor Injection.

    1. In February $2024$, Jia Tan added test files that contained obfuscated code necessary for injecting the backdoor.

4. Deployment.

    1. On February $24$ of $2024$, Jia Tan released version `5.6.0` of XZ Utils, including manually modified source code files containing the malicious code.

    2. Convincing Linux distributions to include the new malicious version.

5. Exploitation.

    The backdoor is activated by changing a function pointer used by `RSA_public_decrypt` for OpenSSH, allowing command execution without authentication by attackers possessing a specific private key.

There are dozens of valuable open source projects like XZ Utils that are mostly driven by a single enthusiast believing in that project. They maintain their projects over years without getting paid and mostly in their free time, even though their code might be an essential part of larger and potentially widely used software projects.

Ultimately, while OSS offers numerous benefits, including transparency, flexibility, and rapid innovation, it also requires a collective commitment to security and sustainability to protect against vulnerabilities and ensure the integrity of the software we all depend on, especially when "$78\%$ of businesses are using open-source software"[open-source usage statistics](https://gitnux.org/open-source-software-statistics).

> [Distribution of Linux-powered websites by global ranking](https://truelist.co/blog/linux-statistics).

## Article review (Teamwork is key to solving complex research problems)

The article "Teamwork is key to solving complex research problems",Elizabeth Culotta address the importance of teamwork in addressing complex research problems. Although the article was published in $1993$ and reflects the context of its time, it provides valuable insights into the dynamics of interdisciplinary collaboration. However, it is worth noting that the article is not exhaustive and leans more towards an opinion piece, sharing experiences from various projects rather than presenting a comprehensive study. Additionally, some of the observations may no longer be as valid due to significant advancements in technology and changes in the way scientific research is conducted.

The article discusses the limitations of interdisciplinary work, such as the challenge of managing team dynamics and the potential for conflict. Culotta shares examples of how teams have overcome these challenges through effective communication, clear organizational structures, and a shared mission. The need for roles within the team is highlighted as a way to address these limitations.

Culotta's article offers valuable insights into the dynamics of successful research teams, emphasizing that interdisciplinary collaboration and strong interpersonal relationships are crucial for solving complex research problems. While the article reflects the context of the early $1990$s and some observations may no longer be fully applicable due to technological advancements, the core principles of effective teamwork remain relevant.

Overall, the article highlights the importance of teamwork in scientific research, recognizing both the challenges and the significant benefits of collaborative efforts. Despite the temporal context, Culotta's observations provide timeless lessons for fostering effective teamwork in any scientific endeavor.
