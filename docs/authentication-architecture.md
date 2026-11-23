Adwuma Track — Authentication Architecture

1. Authentication Method

Primary registration and login method:

- Phone number
- Password
- SMS OTP verification

Email authentication is not required for the initial release.

2. Registration Process

1. User enters full name.
2. User enters phone number.
3. User creates a password.
4. User confirms password.
5. Application validates the information.
6. Supabase Auth creates a phone-based account.
7. SMS verification code is sent.
8. User verifies the OTP.
9. User profile is created.
10. User proceeds to business setup.

3. Login Process

1. User enters phone number.
2. User enters password.
3. Supabase validates credentials.
4. Application retrieves the user's profile.
5. User is directed to their dashboard or business setup.

4. Supabase Services

- Supabase Authentication
- PostgreSQL
- Row Level Security
- SMS provider integration

5. Profiles Table

- id: UUID, references auth.users
- full_name: TEXT
- phone_number: TEXT
- created_at: TIMESTAMPTZ
- updated_at: TIMESTAMPTZ

6. Security Requirements

- Never store plaintext passwords.
- Require phone verification.
- Protect profiles using RLS.
- Validate all user inputs.
- Secure authentication sessions.
- Never expose Supabase service-role keys in the mobile application.

7. Account Recovery

Implement a phone-based account recovery process with OTP verification and secure password updates.

8. Development Status

Architecture approved. Implementation pending.

9. Technology

React Native, Expo, JavaScript, Supabase Auth and PostgreSQL.