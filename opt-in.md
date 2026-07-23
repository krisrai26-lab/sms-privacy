---
layout: default
title: Opt in to Mila SMS
---

# Opt in to Mila SMS

Mila is Kristopher Rai's personal assistant. This is a low-volume,
one-to-one messaging program for scheduling, reminders, and personal or
professional logistics. It does not send marketing or promotional messages.

## Consent and opt-in

To opt in, review the disclosure below, actively check the consent box, and
then select **Continue to text START**. Your messaging app will open with a
pre-filled **START** message to **+1 (786) 833-8144**. You finish opting in
only when you send that message from your mobile number. The inbound START
message records your consent.

<form id="mila-sms-opt-in">
  <fieldset>
    <legend>SMS consent</legend>
    <label>
      <input id="sms-consent" type="checkbox" required>
      I agree to receive low-volume conversational SMS messages from
      Kristopher Rai and Mila, his personal assistant, for scheduling,
      reminders, and personal or professional logistics. Message frequency
      varies. Message and data rates may apply. Consent is not a condition of
      purchase. Reply STOP to opt out or HELP for help.
    </label>
  </fieldset>
  <p>
    <button id="continue-button" type="submit" disabled>
      Continue to text START
    </button>
  </p>
</form>

<p id="consent-instructions" role="status">
  The consent checkbox must be selected before continuing.
</p>

<script>
  (() => {
    const form = document.getElementById("mila-sms-opt-in");
    const consent = document.getElementById("sms-consent");
    const button = document.getElementById("continue-button");
    const instructions = document.getElementById("consent-instructions");

    consent.addEventListener("change", () => {
      button.disabled = !consent.checked;
      instructions.textContent = consent.checked
        ? "Select Continue to open your messaging app, then send START to complete opt-in."
        : "The consent checkbox must be selected before continuing.";
    });

    form.addEventListener("submit", (event) => {
      event.preventDefault();
      if (!consent.checked) return;
      window.location.href = "sms:+17868338144?body=START";
    });
  })();
</script>

You will receive this confirmation after sending START:

> Kristopher Rai: You are opted in to low-volume scheduling, reminder, and
> logistics texts from Mila, Kris's personal assistant. Message frequency
> varies. Msg & data rates may apply. Reply HELP for help or STOP to opt out.

Your mobile information and SMS consent will not be sold, rented, or shared
with third parties or affiliates for marketing or promotional purposes.

Read the [Privacy Policy](https://krisrai26-lab.github.io/sms-privacy/) and
[SMS Terms & Conditions](https://krisrai26-lab.github.io/sms-privacy/terms.html).

If the button does not open your messaging app, manually text **START** to
**+1 (786) 833-8144** after reviewing and agreeing to the disclosure above.
