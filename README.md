

### Julio Vieira
Backend engineer working primarily in Java and Spring Boot. I care more about why a system is shaped the way it is than about how many frameworks went into it.

[LinkedIn](https://www.linkedin.com/in/julio-vieiracb)

---

**Now**

Going deeper into application architecture (domain modeling, layering, authorization design) and embedded systems / IoT, in parallel with day-to-day backend work.

---

**Agenday** — scheduling and service management platform for independent professionals (barbershops, salons), built collaboratively with a small team.

Stack: Java, Spring Boot, Spring Security, PostgreSQL, Flyway · React, TypeScript

A few things I made deliberate calls on:

- **Authorization is role-based at the domain level, not just route-level.** Admin, professional, and client roles map to different permitted actions on the same resources, enforced with `@PreAuthorize` rather than ad-hoc checks scattered through controllers. The cost is more upfront design on what each role can touch; the benefit is that adding a new role later doesn't mean re-auditing every endpoint.
- **Deletions are soft, not hard.** Records carry a `deletedAt` via a shared `BaseEntity` instead of being removed from the table. In a system tied to scheduling and service history, losing a row also means losing the ability to explain what happened later — for disputes, audits, or just debugging a client's complaint. The trade-off is every query needs to be delete-aware, which is more friction than a `DELETE` statement but keeps the data honest.
- Schema evolution is handled with Flyway migrations rather than `ddl-auto`, and errors are normalized through a single `GlobalExceptionHandler` so the API doesn't leak stack traces or inconsistent error shapes to the frontend.

*Repository is private while the project is still being shaped — happy to walk through the code directly.*

---

**Undergraduate thesis (IF Sertão-PE)** — IoT-based air conditioning automation using presence detection. PIR sensor + relay, prototyped in Tinkercad before moving to ESP32 hardware. The interesting part wasn't the sensor reading itself, it was deciding how long the system should wait after detecting no presence before acting — too short and it's annoying, too long and it defeats the purpose.

---

**Stack**

Backend
<br>
<img src="https://skillicons.dev/icons?i=java,spring,postgres,docker&theme=dark" height="40"/>

Frontend
<br>
<img src="https://skillicons.dev/icons?i=ts,react&theme=dark" height="40"/>

Embedded
<br>
<img src="https://skillicons.dev/icons?i=c,arduino&theme=dark" height="40"/>

---

<p align="left">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=juliogitdev&show_icons=true&theme=default&hide_border=true&count_private=true" />
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=juliogitdev&layout=compact&hide_border=true&langs_count=6" />
</p>
