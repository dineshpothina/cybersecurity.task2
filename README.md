# cybersecurity.task2
Phishing traits found (summary)

• Spoofed/typo-squatted sender domain

• From and Return-Path use micros0ft. com (zero instead of "o") - a classic lookalike domain intended to deceive recipients.

Sending host unrelated to claimed sender

• Received shows mail-123.example.net [198.51.100.45] and Message-ID uses mail-123. example.net - not Microsoft infrastructure.

Mismatched visible link text vs actual href

• Visible text / claimed URL:

https://account.microsoft.com

• Actual link target in both plain-text and HTML: http://malicious-example.test/login (and HTML includes ?token=ABC123) - clear redirect to a malicious site.

Urgent / threatening language (social engineering)

• "verify your account within 24 hours" / "may be temporarily suspended" - pressure to act quickly without thinking.

Generic greeting

• Uses "Dear user" instead of a personalized name - common in mass phishing.

Multipart HTML email with hidden target

• HTML body contains an <a href> pointing to the malicious domain; HTML allows link text to be different from the target.

Header / identity discrepancies




Evidence:
- From: "Microsoft Support" <support@micros0ft.com> (typo-squatted domain: micros0ft.com)
- Return-Path: <no-reply@micros0ft.com>
- Received: from mail-123.example.net (mail-123.example.net [198.51.100.45]) — sending host not Microsoft
- Message-ID: <20251021.12345@mail-123.example.net> (Message-ID domain mismatch)
- Body (visible): https://account.microsoft.com
- Actual href: http://malicious-example.test/login?token=ABC123
- Social engineering: "verify your account within 24 hours" (urgent threat)
- Greeting: "Dear user" (generic)
Assessment: Phishing — do not click links or provide credentials.
• Message-ID domain, Return-Path, From, and Received path do not align - inconsistent identity signals.

Potential credential-harvesting behavior

• Link points to /login with a token parameter - typical for fake login pages designed to collect credentials.
