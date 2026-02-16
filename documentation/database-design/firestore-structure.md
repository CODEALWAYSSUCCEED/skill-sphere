# Firestore Structure – Skill Sphere

## Users Collection
users
- userId
- name
- email
- role
- progress

Subcollection:
users/{userId}/reflections
- reflectionId
- skillId
- text
- timestamp

## Skills Collection
skills
- skillId
- title
- description
- sdgNumbers (array)

## Groups Collection
groups
- groupId
- skillId
- mentorId
- members (array of userIds)

## Relationships
- One user → many reflections
- One mentor → many groups
- One skill → many groups
