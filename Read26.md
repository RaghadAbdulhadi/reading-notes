# Managing Django Settings: Issues
Different environments. Usually, you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc).

## Sensitive data

You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.

## Setting Configuration: Different Approaches

There is no built-in universal way to configure Django settings without hardcoding them. But books, open-source and work projects provide a lot of recommendations and approaches on how to do it best.
### settings_local.py
The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS

### Separate settings file for each environment
It allows you to keep all configurations in VCS and to share default settings between developers.

## Setting Structure
Instead of splitting settings by environments, you can split them by the source: Django, third- party apps (Celery, DRF, etc.), and your custom settings.

## Naming Conventions
Give meaningful names to your settings.

Always use the prefix with the project name for your custom (project) settings.

Write descriptions for your settings in comments.

## Django Settings: Best practices
Keep settings in environment variables.

Write default values for production configuration (excluding secret keys and tokens).

Don’t hardcode sensitive settings, and don’t put them in VCS.

Split settings into groups: Django, third-party, project.

Follow naming conventions for custom (project) settings.

### The Settings file is a small but very important part of any Django project. 

## What Is SSH?

SSH, or Secure Shell Protocol, is a remote administration protocol that allows users to access, control, and modify their remote servers over the internet.

### Encryption Techniques
#### Symmetric Encryption
Symmetric encryption is a form of encryption where a secret key is used for both encryption and decryption of a message by both the client and the host. Effectively, anyone possessing the key can decrypt the message being transferred.

#### Asymmetric Encryption
Unlike symmetrical encryption, asymmetrical encryption uses two separate keys for encryption and decryption. These two keys are known as the public key and the private key. Together, both these keys form a public-private key pair.