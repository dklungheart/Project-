# Project-form {
  background: #2a2a2a;
  padding: 20px;
  margin: 20px;
  border-radius: 10px;
}
form input, form textarea {
  width: 100%;
  padding: 10px;
  margin: 5px 0;
  border: none;
  border-radius: 5px;
}
form button {
  background: #ff4747;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 5px;
}const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "your-app.firebaseapp.com",
  projectId: "your-app",
  storageBucket: "your-app.appspot.com",
  messagingSenderId: "xxxxxx",
  appId: "your-app-id"
};<nav>
  <a href="index.html">Home</a>
  <a href="add-review.html">Add Review</a>
</nav>your-app.firebaseapp.comyour-app.appspot.comform.image.valuehttps://www.gstatic.com/firebasejs/10.12.0/firebase-app.js// Firebase SDKs
import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js";
import { getFirestore, collection, addDoc, getDocs } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore.js";

// Your Firebase config here 👇
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "your-app.firebaseapp.com",
  projectId: "your-app",
  storageBucket: "your-app.appspot.com",
  messagingSenderId: "xxxxxx",
  appId: "your-app-id"
};

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);

// Submit form
document.getElementById("reviewForm").addEventListener("submit", async (e) => {
  e.preventDefault();
  const form = e.target;
  const review = {
    title: form.title.value,
    category: form.category.value,
    description: form.description.value,
    rating: form.rating.value,
    image: form.image.value
  };

  try {
    await addDoc(collection(db, "reviews"), review);
    alert("Review added!");
    form.reset();
  } catch (error) {
    console.error("Error adding document: ", error);
  }
});https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore.js<script type="module" src="script.js"></script>
