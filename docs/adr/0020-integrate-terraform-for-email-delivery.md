# [ADR-0020] Integrate Terraform for email-delivery

## Metadata

| Field       | Value                    |
|-------------|--------------------------|
| Date        | 2024-02-06 |
| Status      | Proposed |
| Deciders    | Carol Johnson, Iris Taylor, Henry Brown |

## Context

Our email-delivery implementation needs to handle increasing scale and complexity. The current approach is becoming difficult to maintain and doesn't meet our performance requirements.

Key considerations include:
- Performance requirements for high-volume scenarios
- Team familiarity with the technology
- Long-term maintenance and support
- Integration with existing systems
- Cost implications

## Decision

We will use Kafka for our email-delivery needs. This technology provides the features we need and aligns with our team's expertise.

Key aspects of this decision:
1. We will start with a proof of concept to validate the approach
2. Documentation will be created for the new implementation
3. Training will be provided for team members as needed
4. Monitoring and alerting will be set up from the beginning

## Consequences

### Positive

- Improved scalability for email-delivery
- Better alignment with industry best practices
- Reduced operational complexity
- Enhanced developer experience
- Better observability and debugging capabilities

### Negative

- Initial learning curve for the team
- Migration effort required for existing functionality
- Potential temporary increase in complexity during transition

### Neutral

- Will require updates to our CI/CD pipeline
- May influence future architectural decisions

## Alternatives Considered

### Alternative 1: Continue with current approach

We considered continuing with our existing implementation. This was rejected because it does not address the scalability concerns.

### Alternative 2: Use API-Gateway

We evaluated using API-Gateway. This was not chosen because it added unnecessary complexity for our use case.

## References

- Internal architecture guidelines
- Technology radar evaluation
