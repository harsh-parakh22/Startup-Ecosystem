# Startup-Ecosystem — Core Domain Concepts (Object · Context · Information)

## 1) Authentication & User Management

| Object  | Context        | Key Information |
|---------|----------------|-----------------|
| User    | Auth           | `userId`, `name`, `email`, `role` (admin/investor/startup), `passwordHash`, `createdAt`, `lastLoginAt` |
| Role    | Auth           | `roleId`, `roleName`, `permissions[]` |
| Session | Auth           | `sessionId`, `userId`, `token`, `expiresAt`, `status` |

---

## 2) Startup Profiles & Team

| Object         | Context           | Key Information |
|----------------|-------------------|-----------------|
| Startup        | Profiles          | `startupId`, `name`, `industry`, `location`, `stage`, `valuation`, `fundingNeeded`, `description`, `founderId`, `website`, `logoURL` |
| Founder        | Profiles          | `founderId`, `name`, `bio`, `experience`, `contactInfo` |
| TeamMember     | Profiles          | `memberId`, `startupId`, `name`, `role`, `experience` |
| PitchDeck      | Profiles          | `pitchId`, `startupId`, `fileURL`, `uploadedAt` |

---

## 3) Investors & Funds

| Object        | Context           | Key Information |
|---------------|-------------------|-----------------|
| Investor      | Investor Profiles | `investorId`, `name`, `type` (angel/VC), `industryPreferences[]`, `investmentRange`, `contactInfo` |
| Fund          | Investor Profiles | `fundId`, `investorId`, `fundName`, `size`, `investments[]` |

---

## 4) Deals & Funding Rounds

| Object         | Context         | Key Information |
|----------------|-----------------|-----------------|
| Deal           | Deals           | `dealId`, `startupId`, `investorId`, `amount`, `equityOffered`, `status` (pending/accepted/rejected), `dealDate` |
| FundingRound   | Deals           | `roundId`, `startupId`, `type` (Seed/Series A etc.), `amountRaised`, `leadInvestor`, `closedAt` |
| Valuation      | Deals           | `valuationId`, `startupId`, `valuationAmount`, `valuationDate` |

---

## 5) Ecosystem Components

| Object            | Context         | Key Information |
|-------------------|-----------------|-----------------|
| Incubator         | Ecosystem       | `incubatorId`, `name`, `location`, `programs`, `startupIds[]` |
| Accelerator       | Ecosystem       | `acceleratorId`, `name`, `duration`, `benefits`, `startupIds[]` |
| CoWorkingSpace    | Ecosystem       | `spaceId`, `name`, `location`, `capacity`, `amenities` |
| Mentor            | Ecosystem       | `mentorId`, `name`, `expertise`, `affiliatedOrganizations[]` |

---

## 6) Communication & Collaboration

| Object         | Context         | Key Information |
|----------------|-----------------|-----------------|
| Message        | Communication   | `messageId`, `fromUserId`, `toUserId`, `content`, `sentAt`, `readAt` |
| Meeting        | Communication   | `meetingId`, `startupId`, `investorId`, `agenda`, `scheduledAt`, `status` |
| Notification   | Communication   | `notificationId`, `userId`, `type`, `message`, `createdAt`, `read` |

---

## 7) Analytics & Reports

| Object     | Context           | Key Information |
|------------|-------------------|-----------------|
| Report     | Analytics         | `reportId`, `startupId`, `metrics`, `filters`, `generatedAt`, `generatedBy` |
| Dashboard  | Analytics         | `dashboardId`, `userId`, `widgets[]`, `updatedAt` |
| KPI        | Analytics         | `kpiId`, `name`, `value`, `target`, `period` |

---

## 8) Admin & Audit

| Object     | Context       | Key Information |
|------------|---------------|-----------------|
| AuditLog   | Admin         | `logId`, `actorId`, `action`, `resourceType`, `resourceId`, `timestamp`, `details` |
| SystemConfig | Admin       | `configKey`, `value`, `updatedAt`, `updatedBy` |

---
