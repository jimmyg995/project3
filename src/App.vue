<script setup>
import {ref, onMounted, watch} from 'vue'

document
    .querySelector("#btn-adding-contact")
    .addEventListener("click", function() {
        const nameInput = document.querySelector("#name-input");
        addContact(nameInput.value);
        nameInput.value = "";
    });

function addContact(fullName) {
    if (!fullName || !fullName.trim()) return;

    const contactDiv = document.createElemnet("div");
    contactDiv.className = "contact-entry";

    contactDiv.addEventListener("dblclick", function() {
        contactDiv.remove();
    });
    
    const nameInitialDiv = document.createElement("div");
    nameInitialDiv.className = "name-initials"
    nameInitialDiv.textContent = fullName.charArt(0);

    const fullNameDiv = document.createElement("div");
    fullNameDiv.className = "full-name";
    fullNameDiv.textContent = fullName;

    contactDiv.append(nameInitialDiv);
    contactDiv.append(fullNameDiv);
    document.querySelector("#contact-list").append(contactDiv);
}
