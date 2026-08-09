[中文（Chinese）](./README.md) / 英文（English）
# An_Untitled_ChatAPP
A chat software that has not yet been named...

Since I currently lack the programming language knowledge required for software development, this software exists only in imagination for now.

This repository is currently in the idea collection / brainstorming phase. But feel free to take a look!

# 🌟 This is An_Untitled_ChatAPP!

A cross-platform chat software conceived based on the Open Relay Protocol.

It doesn't want to be "another WeChat" or "another Telegram." Instead, it attempts to answer one question:

If chat software were designed not to "make you reply faster," but to "let you connect more freely," what would it look like?

# 📡 Our Real Thoughts on "Centralized vs. Decentralized"

Many projects get stuck in the dilemma of "must be purely decentralized" or "must be purely centralized," often falling into two traps:

* Going all-in on pure decentralization (like P2P or blockchain): The technical barrier is extremely high. It might take years of development just to get a stable product, and by then users have moved on and the project dies.

* Sticking rigidly to pure centralization (the traditional WeChat/QQ model): While development is simpler, open-sourcing the client becomes meaningless—because the server is a black box. Users cannot verify whether you are secretly recording their chat history.

We don't want to take either extreme. The only thing we truly care about is: users having the power to choose.

Therefore, this project plans to adopt an open architecture we call "Pluggable Relay":

* Out-of-the-box (default mode): We provide official public relay servers through which all encrypted messages are temporarily stored and forwarded. You can download the app and start using it immediately, with network quality guaranteed by us—just as simple as using WeChat.

* Advanced control (power user mode): The client includes a "custom server" option. If you have a technical background, you can deploy your own relay server (we plan to open-source the server code in the future), ensuring that all your chat data flows exclusively through your own server, completely independent of official control.

* Transparent protocol: The communication protocol between the client and relay will be fully public. This means that even if the official servers were to shut down one day, as long as the protocol remains, anyone can write a compatible server to keep this app alive.

## In plain language:

You don't have to endure lag and complex configuration for the sake of "decentralization," nor do you have to hand over all your privacy to a single company for the sake of "convenience."

Default gives you convenience. Advanced gives you freedom.

# 🔐 On Registration: We Give You Choice
We understand that some users want a quick onboarding experience, while others want maximum privacy protection.

Therefore, we provide two registration paths:

* Standard Mode: Use a phone number or email address for quick verification and easy friend discovery. Supports password recovery.

* Anonymous Mode: Only a nickname is required. A key pair is generated locally on your device, without needing any personal identifier.

The two modes can be switched at any time (for example, you can add a phone number to an anonymous account later, for account recovery or to enable contact discovery).

We believe the choice should be yours, not for us to decide the boundaries of your privacy.

# 🛡️ On "Will Anonymous Mode Become a Haven for Bad Actors?"
This is a very real and unavoidable question. Our answer is:

"Anonymous" is not the same as "untraceable," nor is it "unrestrained."

## What we CAN see, and what we CANNOT see?

* Can see: Communication metadata, i.e. who, at what time, from which IP address, using which device, sent a message to which one-time ID. This is basic information that cannot be hidden in any network communication.

* Cannot see: The content of your chats (end-to-end encrypted—even the official relay cannot decrypt them).

## What if bad actors use VPNs to hide their real IP addresses?

Yes, VPNs can hide real IPs. Therefore, our defense system does not rely solely on IP addresses as the single source of truth:

* Device fingerprint anchoring: Each anonymous identity is softly bound to the hardware fingerprint of the device used during first activation. Frequently changing VPNs will not reset your trust score; frequently changing devices will trigger a "cooldown" period.

* Increasing cost of behavior: New anonymous accounts are subject to a very light computational proof-of-work (PoW) when sending messages in their early stage, designed to combat bot registrations. This is imperceptible to regular users.

* Report-and-freeze mechanism: Users can report suspicious accounts with one click. An anonymous ID that receives multiple reports will have its sending privileges frozen, and its metadata logs will be legally retained for potential investigation.

# Can we catch every single bad actor?
No. And we shouldn't try to do so at the expense of everyone's privacy. Given our commitment to end-to-end encryption and no backdoors, if an attacker uses a brand new physical device, a high-quality residential proxy, and manually mimics real human behavior, we cannot (and should not) identify their real identity.

What we CAN do is ensure that any victim can permanently sever the connection with that attacker with just one block.

Our principle is: Make the cost of wrongdoing far exceed its benefit, while always protecting the normal communications of ordinary users.

<br>
<br>

# ✨ Features It Will Support
## 🖐️ Gesture-Based Quick Actions

With a single pull or swipe, you can reply, multi-select messages, create to-do lists within conversations, or even add calendar reminders directly.

The goal is to gradually eliminate the bottom navigation bar and top-right buttons—your fingers become the only controller.

## 🧘 Posture-Aware Feedback
Leveraging the device's built-in accelerometer and gyroscope, the app detects your current holding posture and automatically switches the interface layout:

* Device placed flat (e.g., on a desk during a meeting) → Automatically switches to a linear conversation style for easy scanning.

* Device placed face-down (to prevent snooping or when briefly set aside) → Interface compresses into a semi-transparent floating panel, showing only the latest message keywords.

* Device tilted beyond 15° (e.g., lying in bed or walking) → Interface switches to a fan-shaped rotary layout, with frequently used contacts arranged along the arc of your thumb for one-handed operation.

No settings menu is required. The moment you pick up your phone, the interface is already optimized for your current state.

##🫧 Emotion-Visualizing Input Box (Experimental)

Typing is no longer just cold text input.

While you type, the input box generates subtle particle animations based on local (not cloud-uploaded) semantic analysis:

* Typing "haha" → Warm orange dancing particles appear.

* Typing "oh..." → A slowly settling pale blue ripple emerges in the background.

This is not for show—it's about giving text-based chat back its "tone" and "warmth."

# 🤖 Optional Local AI Assistant (Group Collaborator)
You can choose to invite a local AI assistant into a group chat (e.g., a "Travel Planner" or "Health Manager").

It does not rely on the cloud—it runs entirely on your device. It can follow the discussion among group members and provide suggestions or summaries when needed.

All conversation history stays only on your device. The AI reports nothing to any server.

If you don't trust AI, you can simply choose not to enable it. The choice is yours, not a mandate.

# 🛠 Preliminary Technology Stack Considerations
To strike a balance between "performance" and "maintainability," we are currently leaning toward the following combination:

|Layer|Recommended Technology|Rationale|
|---|---|---|
|Core Engine Layer (encryption, networking)	|Rust|	Extreme performance, memory safety, enormous future optimization potential.|
|Server Side (relay server)|	Go|	High concurrency, high development efficiency, mature ecosystem.|
|Client UI Layer (cross-platform)|	Flutter or Kuikly|	Flutter provides excellent cross-platform UI consistency and animation rendering; Kuikly offers extremely lightweight package size and native-level performance.

The core idea behind this combination: Build the core logic with a hardcore language, and build the UI layer with an efficient cross-platform framework—they don't interfere with each other.

# 🗺️ Questions We Want to Figure Out Together
* Name: It's currently called "An_Untitled_ChatAPP," but clearly that can't be the official name. Any suggestions? (We lean toward imagery like "Nature," "Stars," "Echo"—but not limited to these.)

* Gestures: Are the "swipe to multi-select" and "draw a circle to select messages" ideas intuitive enough? Or are there more natural gesture alternatives?

* Cross-platform Targets: We currently envision covering iOS / Android / Desktop (macOS/Windows/Linux). Do you think we should prioritize dropping any platform early on?

* Anonymous Mode: Does the dual-track system of "standard registration + anonymous mode" alleviate your concerns about "privacy leakage"? Or do you think it's "unnecessary"?

# 🤝 How to Get Involved

If you're interested in this "imaginary chat software," feel free to join in through the following ways:

* Submit an Issue: Suggest new features, or criticize any design as "unrealistic."

* Submit a PR: If you have UI mockups, interaction prototypes, or even just a written description of "what a message bubble should look like," you can place it in the docs/ideas/ directory.

* Technical Advisor: If you're familiar with instant messaging protocols, on-device AI deployment, or cross-platform UI frameworks, feel free to leave your thoughts in an Issue—even if it's just to tell me "this direction is technically unfeasible," that's incredibly valuable.

📄 License

This repository is currently for idea exchange only. The client-side code will tentatively use Apache 2.0 when it is eventually released.

Before any code exists, all text and concepts are licensed under CC BY 4.0 (free to use with attribution).

💬 Final Words

This repository is like an "idea vending machine" sitting on the curb.

If you pass by and think, "Huh, this is kind of interesting," even just leaving a comment saying "keep thinking about it" means a lot to me.

If one day it actually becomes an installable app, it will surely be because someone left a spark of inspiration here.

Thanks for stopping by. 👋
