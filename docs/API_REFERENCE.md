# D-Assist API Reference

## Service Layer APIs

### AuthenticationService

```java
// Login user
public User login(String username, String password)

// Logout current user
public void logout()

// Get current logged-in user
public User getCurrentUser()

// Check if user has specific role
public boolean hasRole(UserRole role)
```

---

### ChatService

```java
// Send query to RAG pipeline
public ChatMessage sendQuery(String query)

// Get user's chat history
public List<ChatMessage> getChatHistory(Long userId)

// Save chat message to database
public void saveChatMessage(ChatMessage message)

// Rate AI response
public void rateResponse(Long messageId, FeedbackRating rating)
```

---

### MedicineService

```java
// Search medicines by name
public List<Medicine> searchByName(String name)

// Search medicines by category
public List<Medicine> searchByCategory(String category)

// Get medicine details
public Medicine getMedicineById(Long id)
```

---

### RAGPipeline

```java
// Process user query through RAG pipeline
public ChatMessage processQuery(String query)
```

---

### InsulinCalculatorService

```java
// Calculate insulin dose
public InsulinDose calculateDose(InsulinDose inputs)

// Calculate carbohydrate dose
public double calculateCarbDose(double carbs, double icr)

// Calculate correction dose
public double calculateCorrectionDose(double currentBG, double targetBG, double isf)
```

---

## Data Layer APIs

### UserRepository

```java
public User findById(Long id)
public User findByUsername(String username)
public void save(User user)
public void update(User user)
public void delete(Long id)
```

### MedicineRepository

```java
public List<Medicine> findAll()
public Medicine findById(Long id)
public List<Medicine> findByName(String name)
public List<Medicine> findByCategory(String category)
```

---

## Complete API documentation will be added during implementation.
