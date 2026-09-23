// ===============================
// FF TOURNAMENT - MAIN JAVASCRIPT
// ===============================

// Mobile menu
function toggleMenu() {
  const menu = document.getElementById("menu");
  menu.classList.toggle("show");
}

// Registration button
function goRegister() {
  document.getElementById("register").scrollIntoView({
    behavior: "smooth"
  });
}

// Registration form
const form = document.getElementById("registrationForm");
const successMessage = document.getElementById("successMessage");

if (form) {
  form.addEventListener("submit", function (event) {
    event.preventDefault();

    const registration = {
      teamName: document.getElementById("teamName").value.trim(),
      leaderName: document.getElementById("leaderName").value.trim(),
      leaderUID: document.getElementById("leaderUID").value.trim(),
      phone: document.getElementById("phone").value.trim(),
      player2: document.getElementById("player2").value.trim(),
      player3: document.getElementById("player3").value.trim(),
      player4: document.getElementById("player4").value.trim(),
      registeredAt: new Date().toLocaleString()
    };

    // Save registration on this device
    let registrations =
      JSON.parse(localStorage.getItem("ffRegistrations")) || [];

    registrations.push(registration);

    localStorage.setItem(
      "ffRegistrations",
      JSON.stringify(registrations)
    );

    // Show success message
    successMessage.classList.remove("hidden");

    form.reset();

    setTimeout(() => {
      successMessage.classList.add("hidden");
    }, 5000);
  });
}

// ===============================
// COUNTDOWN
// ===============================

// Find next Friday 8:00 PM
function getNextFriday() {
  const now = new Date();
  const target = new Date(now);

  const day = now.getDay();
  let daysUntilFriday = (5 - day + 7) % 7;

  // If today is Friday and 8 PM has already passed,
// choose next Friday.
  if (
    daysUntilFriday === 0 &&
    now.getHours() >= 20
  ) {
    daysUntilFriday = 7;
  }

  target.setDate(now.getDate() + daysUntilFriday);
  target.setHours(20, 0, 0, 0);

  return target;
}

let finalDate = getNextFriday();

function updateCountdown() {
  const now = new Date();

  // Refresh target after it passes
  if (now >= finalDate) {
    finalDate = getNextFriday();
  }

  const difference = finalDate - now;

  const days = Math.floor(
    difference / (1000 * 60 * 60 * 24)
  );

  const hours = Math.floor(
    (difference / (1000 * 60 * 60)) % 24
  );

  const minutes = Math.floor(
    (difference / (1000 * 60)) % 60
  );

  const seconds = Math.floor(
    (difference / 1000) % 60
  );

  document.getElementById("days").textContent =
    String(days).padStart(2, "0");

  document.getElementById("hours").textContent =
    String(hours).padStart(2, "0");

  document.getElementById("minutes").textContent =
    String(minutes).padStart(2, "0");

  document.getElementById("seconds").textContent =
    String(seconds).padStart(2, "0");
}

updateCountdown();
setInterval(updateCountdown, 1000);


// ===============================
// CLOSE MENU AFTER CLICK
// ===============================

document.querySelectorAll(".menu a").forEach(link => {
  link.addEventListener("click", () => {
    document.getElementById("menu").classList.remove("show");
  });
});