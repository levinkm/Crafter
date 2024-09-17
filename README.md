# Crafter
Crafter is a powerful CLI tool for creating project structures, bootstrapping applications, and managing development environments. It supports various programming languages and frameworks, with special features for Flutter and Django projects.

## Features

- Create project structures from YAML files
- Generate YAML files from existing projects
- Use and manage project templates
- Inject custom code into specific files
- Containerize applications with Docker
- Add queuing systems (Redis, Kafka, RabbitMQ)
- Special support for Flutter projects (including splash screen generation)

## Installation

```bash
pip install crafter
```

## Usage

### Create a new project

```bash
crafter create project.yaml --template flutter --install-deps
```

### Generate YAML from an existing project

```bash
crafter generate /path/to/project --output project_structure.yaml
```

### Manage templates

```bash
crafter template list
crafter template save my_template.yaml custom_template
crafter template delete custom_template
```

### Containerize a project

```bash
crafter containerize /path/to/project --dockerfile /path/to/dockerfile
```

### Add a queuing system

```bash
crafter add-queue /path/to/project --system redis
```

## YAML Configuration

Here's an example YAML configuration for a Flutter project:

```yaml
template: flutter
name: my_flutter_app
structure:
  lib:
    screens:
      - home_screen.dart
      - settings_screen.dart
  assets:
    images:
      - logo.png
inject_code:
  "lib/main.dart":
    imports: |
      import 'package:flutter/material.dart';
      import 'screens/home_screen.dart';
    main_function: |
      void main() {
        runApp(MyApp());
      }
packages:
  - http: ^0.13.3
  - provider: ^6.0.0
containerize: true
queue_system: redis
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the BSD License.

