<div
  data-chat-widget
  data-style="--chat-widget-primary-color: #188bf6; --chat-widget-active-color:#188bf6 ;--chat-widget-bubble-color: #188bf6"
  data-location-id="cQjrTuEtdOkAp3kjjphO"            
  data-prompt-avatar="https://firebasestorage.googleapis.com/v0/b/highlevel-backend.appspot.com/o/locationPhotos%2FcQjrTuEtdOkAp3kjjphO%2Fchat-widget-person?alt=media&token=b7c030d9-2c00-43cc-8382-562115f0f50c">
</div>
       
<script src="https://widgets.leadconnectorhq.com/loader.js" data-resources-url="https://widgets.leadconnectorhq.com/chat-widget/loader.js" >
</script>

<script
  src="https://code.jquery.com/jquery-3.6.0.min.js"
  integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4="
  crossorigin="anonymous">
</script>

<script>
  
  function waitForElement(selector) {
    return new Promise(resolve => {
        if (document.querySelector(selector)) {
            return resolve(document.querySelector(selector));
        }

        const observer = new MutationObserver(mutations => {
            if (document.querySelector(selector)) {
              observer.disconnect();  
              return resolve(document.querySelector(selector));
            }
        });

        observer.observe(document.body, {
            childList: true,
            subtree: true
        });
    });
  }

  function btnCwSubmit() {
    try {
      alert('ChatWidget Button was clicked!');
      // document.getElementById("demo").innerHTML = "Hello World";
    } catch (error) {
      console.error(error);
    }
  }
  
  $(document).ready(() => {
    waitForElement('lc_text-widget--send-btn')
      .then(element => {
        alert('ChatWidget Button Hooked');
        console.log(element.textContent);
        element.addEventListener("click", btnCwSubmit());
      });
  });

</script>


# chatwidget-test

This is where we test the GHL ChatWidget

