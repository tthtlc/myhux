---
layout: post
title: "AI for checking vulnerabilities in Java Source Code "
tags:
  - Java
  - AI
---

Java source vulnerability analyzer.

<style>
    .external-link-button {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        padding: 10px 20px;
        font-family: Arial, sans-serif;
        font-size: 16px;
        font-weight: bold;
        color: white;
        background: linear-gradient(to right, #8b5cf6, #6366f1);
        border: none;
        border-radius: 8px;
        cursor: pointer;
        transition: all 0.3s ease;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    .external-link-button:hover {
        background: linear-gradient(to right, #7c3aed, #4f46e5);
        transform: translateY(-2px);
        box-shadow: 0 6px 8px rgba(0, 0, 0, 0.15);
    }

    .external-link-button:focus {
        outline: none;
        box-shadow: 0 0 0 3px rgba(139, 92, 246, 0.5);
    }

    .external-link-icon {
        margin-left: 8px;
        width: 16px;
        height: 16px;
    }
</style>


<button class="external-link-button" onclick="openExternalWindow()" aria-label="Open External Link">
    AI Chatbot for Java Source Code Analysis
    <svg class="external-link-icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
    </svg>
</button>
<!-- This chatbot is build using https://openassistantgpt.io/ -->
<script>
    function openExternalWindow() {
        window.open('https://www.openassistantgpt.io/embed/cm3pbjgbp000113g3a9u9037y/window?chatbox=false', '_blank', 'location=yes,height=570,width=520,scrollbars=yes,status=yes');
    }
</script>

<script>
        window.addEventListener("message",function(t){var e=document.getElementById("openassistantgpt-chatbot-iframe"),s=document.getElementById("openassistantgpt-chatbot-button-iframe");"openChat"===t.data&&(console.log("Toggle chat visibility"),e&&s?(e.contentWindow.postMessage("openChat","*"),s.contentWindow.postMessage("openChat","*"),e.style.pointerEvents="auto",e.style.display="block",window.innerWidth<640?(e.style.position="fixed",e.style.width="100%",e.style.height="100%",e.style.top="0",e.style.left="0",e.style.zIndex="9999"):(e.style.position="fixed",e.style.width="480px",e.style.height="65vh",e.style.bottom="0",e.style.right="0",e.style.top="",e.style.left="")):console.error("iframe not found")),"closeChat"===t.data&&e&&s&&(e.style.display="none",e.style.pointerEvents="none",e.contentWindow.postMessage("closeChat","*"),s.contentWindow.postMessage("closeChat","*"))});
</script>

<iframe src="https://www.openassistantgpt.io/embed/cm3pbjgbp000113g3a9u9037y/button?chatbox=false"
    style="z-index: 50; margin-right: 6px; margin-bottom: 6px; position: fixed; right: 0; bottom: 0; width: 60px; height: 60px; border: 0; border: 2px solid #e2e8f0; border-radius: 50%; color-scheme: none; background: none;box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);"
    id="openassistantgpt-chatbot-button-iframe"></iframe>
  <!-- This chatbot is build using https://openassistantgpt.io/ -->
  <iframe src="https://www.openassistantgpt.io/embed/cm3pbjgbp000113g3a9u9037y/window?chatbox=false&withExitX=true"
    style="z-index: 50; margin-right: 6px; margin-bottom: 98px; display: none; position: fixed; right: 0; bottom: 0; pointer-events: none; overflow: hidden; height: 65vh; border: 2px solid #e2e8f0; border-radius: 0.375rem; box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06); width: 480px;"
    allow="clipboard-read; clipboard-write"
    allowfullscreen id="openassistantgpt-chatbot-iframe">
</iframe>
