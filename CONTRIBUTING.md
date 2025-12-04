# Contributing to D-Assist

Thank you for considering contributing to D-Assist! We welcome contributions from the community.

## How to Contribute

### Reporting Bugs
- Use the GitHub issue tracker
- Describe the bug in detail
- Include steps to reproduce
- Mention your environment (OS, Java version, etc.)

### Suggesting Features
- Open an issue with the "enhancement" label
- Clearly describe the feature and its use case
- Explain how it benefits pharmacy professionals

### Submitting Pull Requests

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Make your changes**
4. **Write or update tests**
5. **Ensure all tests pass**
   ```bash
   mvn test
   ```
6. **Commit your changes**
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
7. **Push to your fork**
   ```bash
   git push origin feature/AmazingFeature
   ```
8. **Open a Pull Request**

## Code Standards

### Java Coding Conventions
- Follow standard Java naming conventions
- Use meaningful variable and method names
- Keep methods small and focused
- Write JavaDoc comments for public methods

### Code Style
- Use 4 spaces for indentation (no tabs)
- Maximum line length: 120 characters
- Place opening braces on the same line
- Use proper spacing around operators

### Documentation
- Update README.md if adding new features
- Add JavaDoc comments for all public classes and methods
- Update USER_GUIDE.md for user-facing changes

### Testing
- Write unit tests for new functionality
- Maintain test coverage above 80%
- Ensure all tests pass before submitting PR
- Include integration tests for complex features

### Commit Messages
- Use clear, descriptive commit messages
- Start with a verb (Add, Fix, Update, Remove)
- Keep first line under 50 characters
- Add detailed description if needed

Example:
```
Add insulin dose calculator feature

- Implement calculation logic for ICR and ISF
- Create calculator UI with input validation
- Add unit tests for dose calculations
```

## Development Setup

1. **Install Prerequisites**
   - Java JDK 17 or higher
   - Apache Maven 3.8+
   - IDE with JavaFX support (recommended: IntelliJ IDEA)

2. **Clone and Build**
   ```bash
   git clone https://github.com/Qwen88wen/D-Assist.git
   cd D-Assist
   mvn clean install
   ```

3. **Run Tests**
   ```bash
   mvn test
   ```

4. **Run the Application**
   ```bash
   mvn javafx:run
   ```

## Project Structure

- `src/main/java/com/dassist/controller/` - UI controllers
- `src/main/java/com/dassist/model/` - Data models
- `src/main/java/com/dassist/service/` - Business logic
- `src/main/java/com/dassist/rag/` - RAG pipeline components
- `src/main/resources/fxml/` - JavaFX layouts
- `src/test/` - Test files

## Questions?

If you have questions, feel free to:
- Open an issue for discussion
- Contact the maintainers
- Check existing documentation in `docs/`

Thank you for contributing to D-Assist!
