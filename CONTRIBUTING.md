# Contributing to KRISHI KRANTHI

Thank you for being interested in contributing! This document provides guidelines and instructions for contributing to the project.

## Code of Conduct

By participating in this project, you agree to maintain a respectful and inclusive environment. We expect:

- Respectful communication
- Professional behavior
- No harassment or discrimination
- Constructive feedback

Report any violations to the project maintainers.

## How to Contribute

### Reporting Issues

If you find a bug or have a suggestion:

1. Check the existing issues to avoid duplicates
2. Provide a clear title and description
3. Include steps to reproduce (for bugs)
4. Add relevant labels
5. Be specific about what you expected vs what happened

### Suggesting Improvements

Feature suggestions are welcome! Please:

1. Use the label "enhancement"
2. Describe the use case
3. Explain why this would be beneficial
4. Provide examples if possible

### Setting Up Development Environment

1. Fork the repository
2. Clone your fork: `git clone https://github.com/yourname/krishi-kranthi.git`
3. Create a virtual environment: `python -m venv venv`
4. Activate it:
   - Windows: `venv\Scripts\activate`
   - Mac/Linux: `source venv/bin/activate`
5. Install dependencies: `pip install -r requirements.txt`
6. Create a branch: `git checkout -b feature/your-feature-name`

### Coding Guidelines

**Python Style:**
- Follow PEP 8
- Use 4 spaces for indentation
- Max line length is 100 characters
- Use meaningful variable names
- Add docstrings to functions

**Example:**
```python
def get_product_by_id(product_id):
    """Retrieve product from database by ID.
    
    Args:
        product_id (int): The product identifier
        
    Returns:
        dict: Product data or None if not found
    """
    # implementation here
    pass
```

**JavaScript Style:**
- Use semicolons
- Use 2 spaces for indentation
- Use meaningful variable names
- Avoid global variables
- Comment complex logic

**HTML/CSS:**
- Use semantic HTML5
- Keep CSS organized
- Use class names following BEM convention when possible
- Comment non-obvious CSS rules

### Making Changes

1. Make sure your code works locally
2. Test your changes thoroughly
3. Add tests if you're adding new functionality
4. Keep commits atomic and focused
5. Write clear commit messages

### Commit Messages

Use conventional commits:

- `feat:` for new features
- `fix:` for bug fixes
- `docs:` for documentation
- `style:` for formatting
- `refactor:` for code reorganization
- `test:` for test additions
- `chore:` for maintenance

Example: `feat: add price history tracking for products`

### Pushing Changes

1. Push to your fork: `git push origin feature/your-feature-name`
2. Go to GitHub and create a Pull Request
3. Fill in the PR template
4. Link any related issues
5. Wait for review

### Pull Request Guidelines

**Your PR should:**

- Have a descriptive title
- Include a clear description of changes
- Reference any related issues
- Include tests if applicable
- Pass all CI checks
- Have clean commit history

**In the description, explain:**

- What problem does this solve?
- How does it solve it?
- Are there any breaking changes?
- Any new dependencies?

### Review Process

1. A maintainer will review your PR
2. They may request changes
3. Make requested changes in new commits
4. Once approved, your PR will be merged

## Project Structure

Familiarize yourself with:

- `app/` - Flask application code
- `database/` - SQL schemas and migrations
- `docs/` - Documentation
- `tests/` - Test files
- `config/` - Configuration files

## Testing

Before submitting a PR:

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=app

# Run specific test
pytest tests/test_auth.py -v
```

New features should include tests. Aim for at least 80% code coverage.

## Documentation

If your change affects:

- **User functionality**: Update README.md
- **Setup process**: Update docs/SETUP.md
- **Database**: Update docs/DATABASE.md
- **APIs**: Update docs/API.md

## Local Testing Checklist

Before submitting PR:

- [ ] Code follows PEP 8 style
- [ ] All tests pass locally
- [ ] No console errors
- [ ] Functionality tested in browser
- [ ] Documentation updated
- [ ] Commit messages are clear
- [ ] No hardcoded values
- [ ] No debug statements left

## Areas We Need Help

- Bug fixes
- Performance improvements
- Documentation
- Test coverage
- UI/UX improvements
- Mobile optimization
- Feature implementations

## Questions?

Feel free to:
- Open a discussion issue
- Email project maintainers
- Check existing documentation

## Recognition

Contributors will be recognized in:
- README.md
- Release notes
- Project dashboard

Thank you for contributing to make agriculture more accessible!

---

**Last Updated:** February 2026
