
Firestore Structure – Skill Sphere

---

### 1️⃣ Users Collection

**Collection:** `users`

Each document ID = Firebase Authentication UID

**Fields:**
- **name** (string)
- **email** (string)
- **role** (string: "learner" or "mentor")
- **createdAt** (timestamp)
- **progress** (object or number)

**Subcollection:**
- `users/{userId}/reflections`

Each reflection document contains:
	- **skillId** (string)
	- **text** (string)
	- **createdAt** (timestamp)

**Relationship:**
- One user → many reflections
- One user → can join many groups

---

### 2️⃣ Skills Collection

**Collection:** `skills`

**Fields:**
- **title** (string)
- **description** (string)
- **sdgNumbers** (array of numbers, e.g. `[4, 8]`)
- **impactStatement** (string)
- **createdAt** (timestamp)

**Relationship:**
- One skill → many reflections
- One skill → many learning groups

---

### 3️⃣ Groups Collection

**Collection:** `groups`

**Fields:**
- **title** (string)
- **skillId** (string reference to skills)
- **mentorId** (string reference to users)
- **members** (array of userIds)
- **meetingTime** (string)
- **createdAt** (timestamp)

**Relationship:**
- One mentor → many groups
- One group → many members
- One skill → many groups
