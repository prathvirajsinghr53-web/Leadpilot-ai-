# Leadpilot-ai-
Leadpilot ai saas 
{
  "entities": {
    "UserProfile": {
      "collection": "users",
      "fields": {
        "uid": { "type": "string", "description": "User unique identifier" },
        "name": { "type": "string", "description": "User full name" },
        "email": { "type": "string", "description": "User email address" },
        "businessName": { "type": "string", "description": "Business or organization name", "optional": true },
        "photoURL": { "type": "string", "description": "Profile picture URL", "optional": true },
        "createdAt": { "type": "string", "description": "Account creation timestamp" },
        "updatedAt": { "type": "string", "description": "Last update timestamp" },
        "currentPlan": { "type": "string", "description": "Current subscription plan (Free / Pro / Business)" },
        "trialStartDate": { "type": "string", "description": "Trial start date" },
        "trialEndDate": { "type": "string", "description": "Trial expiry date" },
        "referralId": { "type": "string", "description": "Unique referral code (e.g. LP-RAJ12345)" },
        "referredByUserId": { "type": "string", "description": "UID of referrer", "optional": true },
        "referredByCode": { "type": "string", "description": "Referral code used to sign up", "optional": true },
        "verifiedReferralCount": { "type": "number", "description": "Count of verified referrals" },
        "pendingReferralCount": { "type": "number", "description": "Count of pending referrals" },
        "claimedMilestones": { "type": "object", "description": "Map of claimed reward milestones", "optional": true },
        "bonusTrialDays": { "type": "number", "description": "Total bonus trial days unlocked", "optional": true }
      }
    },
    "ReferralRecord": {
      "collection": "referrals",
      "fields": {
        "id": { "type": "string", "description": "Unique referral record ID (referrerId_referredId)" },
        "referrerUserId": { "type": "string", "description": "UID of the referrer" },
        "referralId": { "type": "string", "description": "Referral code used" },
        "referredUserId": { "type": "string", "description": "UID of the referred user" },
        "referredUserName": { "type": "string", "description": "Name of the referred user" },
        "referredUserEmail": { "type": "string", "description": "Email of the referred user" },
        "createdAt": { "type": "string", "description": "Attribution creation timestamp" },
        "status": { "type": "string", "description": "Status: pending, verified, rejected" },
        "verificationDate": { "type": "string", "description": "Date when verified", "optional": true },
        "accountActivated": { "type": "boolean", "description": "Whether referred account is active" },
        "activityCount": { "type": "number", "description": "Number of actions/leads completed by referred user" },
        "hasPurchasedPlan": { "type": "boolean", "description": "Whether referred user has purchased a subscription" },
        "verificationNotes": { "type": "string", "description": "Notes explaining verification state", "optional": true }
      }
    },
    "AdminReferralRules": {
      "collection": "admin_settings",
      "fields": {
        "minimumLeadsRequired": { "type": "number", "description": "Minimum leads required to verify" },
        "requireEmailVerification": { "type": "boolean", "description": "Require verified email" },
        "requirePaidSubscription": { "type": "boolean", "description": "Require subscription purchase" },
        "maxRewardsPerUser": { "type": "number", "description": "Max rewards per user" },
        "rewardExpirationDays": { "type": "number", "description": "Days before reward expires" }
      }
    },
    "Lead": {
      "collection": "users/{userId}/leads",
      "fields": {
        "id": { "type": "string", "description": "Unique Lead ID" },
        "userId": { "type": "string", "description": "Owner user ID" },
        "name": { "type": "string", "description": "Lead full name" },
        "phone": { "type": "string", "description": "Contact phone number" },
        "email": { "type": "string", "description": "Contact email address" },
        "company": { "type": "string", "description": "Lead company name", "optional": true },
        "product": { "type": "string", "description": "Requirement or product of interest" },
        "leadSource": { "type": "string", "description": "Acquisition source (Inbound, Referral, LinkedIn, etc.)" },
        "budget": { "type": "number", "description": "Deal value / budget amount" },
        "notes": { "type": "string", "description": "Lead notes" },
        "status": { "type": "string", "description": "Pipeline stage (NEW, CONTACTED, QUALIFIED, PROPOSAL, NEGOTIATION, WON, LOST)" },
        "followUpDate": { "type": "string", "description": "Follow-up due date (YYYY-MM-DD)", "optional": true },
        "createdAt": { "type": "string", "description": "Record creation timestamp" },
        "updatedAt": { "type": "string", "description": "Record update timestamp" },
        "aiScore": { "type": "number", "description": "AI Lead Score (0-100)", "optional": true },
        "aiCategory": { "type": "string", "description": "HOT, WARM, COLD", "optional": true },
        "aiReasoning": { "type": "string", "description": "Grounding reason for score", "optional": true },
        "aiSuggestedNextAction": { "type": "string", "description": "Recommended next action", "optional": true },
        "aiNextActionReason": { "type": "string", "description": "Why this action is recommended", "optional": true },
        "aiRecommendedChannel": { "type": "string", "description": "WhatsApp, Email, Call", "optional": true },
        "isFollowUpCompleted": { "type": "boolean", "description": "Whether follow-up is done", "optional": true }
      }
    }
  }
}
