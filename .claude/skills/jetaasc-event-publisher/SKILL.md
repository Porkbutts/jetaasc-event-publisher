---
name: jetaasc-event-publisher
description: Publish JETAASC (JET Alumni Association of Southern California) events to multiple platforms. Use when user wants to publish an event, draft an event, create event descriptions, or share events to Wix blog, Google Calendar, Discord, or Facebook. Triggers include "publish event", "draft event", "create event post", "share to wix/calendar/discord/fb", or any JETAASC event-related publishing task.
---

# JETAASC Event Publisher

Publish JETAASC events to multiple platforms: Wix Blog, Google Calendar, Discord, and Facebook.

## Workflow

### 1. Collect Event Information

Gather from user:
- **Title**: Event name
- **Date/Time**: Start (and end if applicable)
- **Location**: Venue name and address
- **Description**: What the event is about
- **Cost**: Price (optional, include member/non-member pricing if applicable)
- **RSVP Link**: Google Form link (optional)
- **Flyer/Image**: Event artwork URL or file

### 2. Publish to Wix Blog

Use Wix MCP tools. See [references/platforms.md](references/platforms.md) for site ID, API endpoints, category/tag IDs. See [references/wix-blog-format.md](references/wix-blog-format.md) for Ricos JSON structure.

Steps:
1. Upload flyer to Wix Media Manager (Import File endpoint)
2. Select appropriate tags by analyzing event title, description, and location
3. Create draft post with title, image, richContent, category, and tags
4. Share draft preview link for user confirmation
5. If user has feedback, update draft via PATCH endpoint. Repeat until approved.
6. On approval, publish draft
7. Return published post URL

### 3. Publish to Google Calendar

Add event to JETAASC Public Calendar. See [references/platforms.md](references/platforms.md) for API details.

Required: Google Calendar API credentials configured.

### 4. Publish to Discord

Create Discord scheduled event. See [references/platforms.md](references/platforms.md) for API details.

Required: Discord bot with Manage Events permission.

### 5. Facebook (Manual)

Provide formatted content for manual posting. See [references/platforms.md](references/platforms.md) for format.

## Quick Reference

| Platform | Method | Status |
|----------|--------|--------|
| Wix Blog | API (Wix MCP) | Ready |
| Google Calendar | API | Requires setup |
| Discord | API | Requires setup |
| Facebook | Manual | Copy/paste |
