<script
  src="https://code.jquery.com/jquery-3.6.0.min.js"
  integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4="
  crossorigin="anonymous">
</script>


<iframe src="https://meetings.hubspot.com/mike-khlebas" >

<script>
  
  function waitForElementToDisplay(selector, callback, checkFrequencyInMs, timeoutInMs) {
    var startTimeInMs = Date.now();
    (function loopSearch() {
      if (document.querySelector(selector) != null) {
        callback();
        return;
      }
      else {
        setTimeout(function () {
          if (timeoutInMs && Date.now() - startTimeInMs > timeoutInMs)
            return;
          loopSearch();
        }, checkFrequencyInMs);
      }
    })();
  }


  function waitForElement(selector) {
    return new Promise(resolve => {
        if (document.querySelector(selector)) {
            console.log('FOUND selector');
            alert('FOUND selector');
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
    alert('document READY!');
    
    waitForElementToDisplay("#lc_text-widget--send-btn",() => {
      alert('ChatWidget Button Hooked');
      console.log(element.textContent);
      element.addEventListener("click", btnCwSubmit());
    }, 1000, 9000);
  
  /*
     waitForElement('#lc_text-widget--send-btn')
      .then(element => {
        alert('ChatWidget Button Hooked');
        console.log(element.textContent);
        element.addEventListener("click", btnCwSubmit());
      });
  */
  });

  
</script>


# chatwidget-test

This is where we test the GHL ChatWidget

Using some setInverval code


