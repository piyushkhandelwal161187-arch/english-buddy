# English Buddy — आसान सेटअप

The app opens from a secure internet link and can be installed on the phone's home screen. Practice lessons work without an API key. “Talk to Buddy” needs an Anthropic API key and internet.

ऐप एक सुरक्षित इंटरनेट लिंक से खुलता है और फ़ोन की home screen पर install किया जा सकता है। Practice बिना API key के चलता है। “Talk to Buddy” के लिए Anthropic API key और इंटरनेट चाहिए।

## 1. Get an API key / API key बनाएँ

1. Open `console.anthropic.com` and sign up or sign in.  
   `console.anthropic.com` खोलकर sign up या sign in करें।
2. Add a small amount of credit in Billing.  
   Billing में थोड़ा credit जोड़ें।
3. Open **API Keys**, choose **Create Key**, and copy the new key.  
   **API Keys** में जाकर **Create Key** दबाएँ और नई key copy करें।
4. Keep the key private. Do not send it in WhatsApp or share a screenshot of it.  
   Key को private रखें। इसे WhatsApp पर न भेजें और इसका screenshot share न करें।

## 2. Install on the Android phone / Android फ़ोन पर install करें

1. Ask Papa for the app's internet link and open it in **Google Chrome**.  
   पापा से ऐप का इंटरनेट लिंक लें और उसे **Google Chrome** में खोलें।
2. Tap Chrome's **⋮ menu → Install app** (sometimes shown as **Add to Home screen**).  
   Chrome का **⋮ menu → Install app** दबाएँ (कभी-कभी **Add to Home screen** लिखा होता है)।
3. Confirm **Install**. Open **Buddy** from the new home-screen icon each day.  
   **Install** पक्का करें। रोज़ home screen के नए **Buddy** icon से ऐप खोलें।

### Fallback: saved file / विकल्प: सेव की हुई फ़ाइल

If the internet link is temporarily unavailable, `index.html` can still be opened as a saved file for lessons, listening, stars, and parent settings. On phones, the microphone cannot work from a saved file, so **Your turn** and **Talk to Buddy** voice input require the HTTPS internet link.

अगर इंटरनेट लिंक कुछ समय उपलब्ध न हो, तो lessons, listening, stars और parent settings के लिए सेव की हुई `index.html` फ़ाइल खोली जा सकती है। फ़ोन पर सेव की हुई फ़ाइल से microphone काम नहीं कर सकता, इसलिए **Your turn** और **Talk to Buddy** voice input के लिए HTTPS इंटरनेट लिंक ज़रूरी है।

## 3. Allow the microphone / माइक्रोफ़ोन की अनुमति दें

When Chrome asks for microphone access, tap **Allow**. If it was denied earlier:

जब Chrome microphone की अनुमति माँगे, **Allow** दबाएँ। अगर पहले मना कर दिया था:

1. Open Android **Settings → Apps → Chrome → Permissions → Microphone**.
2. Choose **Allow while using the app**.
3. Return to Chrome and open the installed app or internet link again.

Speech recognition uses Google's online speech service, so “Your turn” and voice chat need internet. Listening to targets and all lesson text remain inside the app.

Speech recognition Google की online service उपयोग करता है, इसलिए “Your turn” और voice chat के लिए इंटरनेट चाहिए। Lesson का text ऐप में ही रहता है।

## 4. Set up Buddy / Buddy को तैयार करें

1. Open the **Parents** tab. The default PIN is `1234`.  
   **Parents** tab खोलें। Default PIN `1234` है।
2. Open **Buddy API / बडी एपीआई**, paste the API key, and tap **Save / सहेजें**.
3. Tap **Test key / कुंजी जाँचें**. A green success message means Buddy is ready.
4. Choose a model:
   - **Claude Opus 4.8** — best conversation quality and the default.
   - **Claude Haiku 4.5** — lower-cost economy choice.
5. Change the parent PIN in **Change PIN / पिन बदलें**.

The API key is masked and saved only in Chrome's local storage on that device. It is never written into `index.html`. Clearing Chrome site data will also remove the key, progress, settings, and transcripts.

API key केवल उस फ़ोन के Chrome local storage में save होती है; `index.html` में नहीं लिखी जाती। Chrome का site data clear करने पर key, progress, settings और transcripts भी मिट जाएँगे।

## 5. Assignment Upload / असाइनमेंट अपलोड

1. Open the PIN-locked **Parents** tab, then open **School Assignment / स्कूल का काम**. The saved API key is required.  
   PIN से सुरक्षित **Parents** tab खोलें, फिर **School Assignment / स्कूल का काम** खोलें। Saved API key ज़रूरी है।
2. Add an optional parent note, tap **Upload assignment photo / असाइनमेंट फोटो अपलोड करें**, and choose the camera or gallery.  
   चाहें तो parent note लिखें, **Upload assignment photo / असाइनमेंट फोटो अपलोड करें** दबाएँ और camera या gallery चुनें।
3. Check and edit the extracted title, spelling words, reading lines, questions, answers, notes, and summary. Tap **Save / सहेजें**. The new pack appears automatically in **Practice**, and Buddy coaches the active school task.  
   निकला हुआ title, spelling words, reading lines, सवाल, जवाब, notes और summary जाँचकर बदलें। **Save / सहेजें** दबाएँ। नया pack अपने-आप **Practice** में आएगा और Buddy उसी school task का अभ्यास कराएगा।
4. When the work is complete, tap **Mark done / पूरा हुआ** to remove it from Buddy's prompt and earn the special Homework Hero badge.  
   काम पूरा होने पर **Mark done / पूरा हुआ** दबाएँ। वह Buddy के prompt से हट जाएगा और Homework Hero badge मिलेगा।

The photo is resized, sent once for reading, and immediately discarded. The app never saves the photo in browser storage.

फोटो को छोटा करके केवल पढ़ने के लिए एक बार भेजा जाता है और तुरंत हटा दिया जाता है। ऐप फोटो को browser storage में कभी save नहीं करता।

## 6. A simple daily routine / रोज़ का आसान अभ्यास

- **10 minutes Practice:** listen, speak, and try a few words, sentences, or a story.
- **10 minutes Buddy:** talk about school, family, animals, food, a festival, or a story.
- Stop while it is still fun. Short daily practice is better than one long session.

- **10 मिनट Practice:** सुनें, बोलें और कुछ words, sentences या story करें।
- **10 मिनट Buddy:** school, family, animals, food, festival या story पर बात करें।
- अभ्यास छोटा और मज़ेदार रखें। रोज़ थोड़ा अभ्यास एक लंबे session से बेहतर है।

At the default 20-minute daily limit, normal child-sized replies should usually cost only a few rupees per day, but the exact amount depends on the selected model, conversation length, exchange rate, and Anthropic's current pricing. Use the Haiku economy model if you want the lowest cost, and check the Anthropic console usage page occasionally.

Default 20-minute limit पर आम तौर पर खर्च कुछ रुपये प्रतिदिन होना चाहिए, लेकिन सही खर्च model, बातचीत की लंबाई, exchange rate और Anthropic की मौजूदा pricing पर निर्भर है। कम खर्च के लिए Haiku economy model चुनें और कभी-कभी Anthropic console में usage देखें।

## Quick help / छोटी मदद

- **Buddy says it is napping:** check internet, API credit, and **Error log / त्रुटि लॉग** in Parents.
- **Microphone does not work:** open the HTTPS app link in Chrome (not a saved file), allow microphone permission, and connect to the internet.
- **Daily time is over:** Buddy unlocks the next day; a parent can also use **Reset today's time / आज का समय रीसेट करें**.
- **No voice is heard:** raise media volume and choose another English voice under **Buddy's voice / बडी की आवाज़**.
