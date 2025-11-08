# Example: Meeting Summary Capture

## Before (Raw Input)

```
Had a good meeting today with the product and design teams about authentication.
We talked about moving to passwordless auth using passkeys. Sarah brought up
that we need to support legacy systems, so we can't go all-in yet. Mike showed
designs for the new flow - looks great. We decided to do a phased rollout:
Phase 1 is passkeys in web, Phase 2 is mobile, Phase 3 is legacy support.
Sarah will write the spec, Mike will handle design across all phases, and I'll
coordinate engineering. We also talked about the performance issues with the
current auth - not a blocker but something we should keep an eye on. The new
architecture should fix that anyway. Need to talk to infra about deployment,
and we'll need a migration plan for existing users.
```

## After (Captured in Notion)

### Meeting Summary: Passwordless Authentication Strategy

**Date:** November 9, 2025
**Attendees:** Sarah (Product), Mike (Design), Engineering Lead
**Duration:** 1 hour
**Status:** Decisions Made

---

## Key Decisions

### Decision 1: Implement Passwordless Authentication via Passkeys
- **Decision:** Migrate to passkey-based authentication
- **Rationale:** Improved security and user experience
- **Phase Approach:** Phased rollout required due to legacy system constraints

### Decision 2: Phased Rollout Strategy
- **Phase 1:** Passkeys in web applications
- **Phase 2:** Mobile app support
- **Phase 3:** Legacy system support and migration
- **Rationale:** Allows gradual adoption while maintaining backward compatibility

---

## Action Items

| Owner | Task | Deadline | Status |
|-------|------|----------|--------|
| Sarah (Product) | Write passwordless auth specification with phase requirements | This week | Not Started |
| Mike (Design) | Create design mockups for all authentication flows across phases | End of week | In Progress |
| Engineering Lead | Coordinate engineering effort and infrastructure planning | Next sprint | Not Started |
| Infrastructure | Plan deployment strategy and production rollout approach | TBD | Not Started |

---

## Discussion Topics

### Passwordless Authentication
- Passkeys provide strong security posture
- User experience benefits over traditional passwords
- Industry standard approach (WebAuthn/FIDO2)

### Legacy System Constraints
- Cannot immediately deprecate password authentication
- Existing systems require continued support
- Migration path needed for users on legacy platforms

### Performance Considerations
- Current auth system has performance overhead
- New architecture should resolve existing performance issues
- Not a blocker for implementation but important improvement

### Migration Planning
- Need clear plan for existing user migration
- Gradual rollout reduces risk
- Each phase builds on previous phase

---

## Next Steps

1. **This Week:** Sarah delivers detailed specification
2. **End of Week:** Design mockups finalized for review
3. **Next Sprint:** Engineering begins Phase 1 (web) implementation
4. **Parallel:** Infrastructure team plans deployment and migration strategy
5. **TBD:** User communication plan for authentication transition

---

## Related Documents

- [Authentication Architecture Decision Record](notion://decision-record-url)
- [Security Requirements Specification](notion://spec-url)
- [Q4 Product Roadmap](notion://roadmap-url)
- [Infrastructure Planning](notion://infra-url)

## Tags

`authentication` `security` `product-initiative` `phased-rollout` `decision-record`

## Follow-up Items

- [ ] Schedule follow-up meeting after specs are written
- [ ] Plan QA testing strategy for each phase
- [ ] Create user communication plan
- [ ] Schedule infrastructure review of deployment plan

---

## Notes

- **Performance improvement** is a nice-to-have benefit of new architecture
- **Backward compatibility** is critical for adoption success
- **Phasing** reduces implementation risk and allows for feedback cycles

**Owner:** Sarah (Product) | **Last Updated:** November 9, 2025 | **Next Review:** November 23, 2025
