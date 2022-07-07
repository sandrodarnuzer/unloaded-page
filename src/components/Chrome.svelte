<script>
  import chrome from "../assets/chrome.png";

  let host = window.location.host;
  let showDetails = false;

  function toggleDetails() {
    showDetails = !showDetails;
  }
</script>

<div
  class="fixed top-0 left-0 h-screen w-screen bg-white dark:bg-[#202124] -z-10"
/>
<div class="bg-white dark:bg-[#202124] w-full px-10 xs:px-20">
  <div
    class="flex flex-col gap-4 mt-40 text-[#5F6368] dark:text-[#9AA0A6] max-w-[40rem] mx-auto"
  >
    <img
      src={chrome}
      alt=""
      class="block w-[72px] h-[72px] mb-6 dark:block filter dark:invert"
    />
    <h1 class="text-2xl font-medium text-[#202124] dark:text-[#9AA0A6]">
      Die Website ist nicht erreichbar
    </h1>
    <p>
      Die Server-IP-Adresse von
      <span class="font-bold">{host}</span>
      wurde nicht gefunden.
    </p>
    <div>
      <p class="mb-">Versuche Folgendes:</p>
      <ul class="list-disc ml-12">
        <li>Verbindung prüfen</li>
        <li>
          <a
            href="#buttons"
            class="text-[#1A73E8] dark:text-[#8AB5F8]"
            on:click|preventDefault={toggleDetails}
            >Proxy, Firewall und DNS-Konfiguration prüfen</a
          >
        </li>
      </ul>
    </div>
    <div class="text-xs text-">ERR_NAME_NOT_RESOLVED</div>
    <div class="flex justify-between text-sm mt-8">
      <button
        class=" py-1.5 px-4 rounded-[0.25rem] bg-white border border-[#9AA0A6] hover:bg-[#F8F9FA] dark:bg-[#202124] dark:border-[#5F6368] dark:text-[#8AB5F8] dark:hover:bg-[#303339]"
        on:click={toggleDetails}
        >{showDetails ? "Details ausblenden" : "Details"}</button
      >
      <button
        class="py-1.5 px-4 rounded-[0.25rem] bg-[#1A73E8] text-white dark:bg-[#8AB5F8] dark:text-[#202124]"
        on:click={() => window.location.reload()}>Neu laden</button
      >
    </div>
    {#if showDetails}
      <div class="mt-4 mb-32 flex flex-col gap-6">
        <div>
          <span class="block font-bold mb-2"
            >Bitte überprüfe deine Internetverbindung.</span
          >
          <p class="text-[#777777]">
            Check any cables and reboot any routers, modems, or other network
            devices you may be using. Also check that any proxy server currently
            in use is reachable and configured correctly.
          </p>
        </div>
        <div>
          <span class="block font-bold mb-2"
            >Überprüfe die DNS-Einstellungen.</span
          >
          <p class="text-[#777777]">
            Wenn du weitere Informationen dazu benötigst, kann dir dein
            Netzwerkadministrator weiterhelfen.
          </p>
        </div>
        <div>
          <span class="block font-bold mb-2"
            >Deaktiviere die Netzwerkvorhersage.</span
          >
          <p class="text-[#777777]">
            Öffne das Chromium-Menü > Einstellungen > Erweiterte Einstellungen
            anzeigen und deaktiviere "Vorhersagefunktion zum schnelleren Laden
            von Seiten verwenden ". Falls das Problem nicht dadurch verursacht
            wurde, empfehlen wir, diese Option für eine verbesserte Leistung
            wieder zu aktivieren.
          </p>
        </div>
        <div>
          <span class="block font-bold mb-2"
            >Erlaube Chromium in deinen Firewall- und Virenschutzeinstellungen
            den Zugriff auf das Netzwerk.</span
          >
          <p class="text-[#777777]">
            Falls das Programm schon in der Liste mit erlaubtem Netzwerkzugriff
            eingetragen ist, entferne es aus der Liste und füge es noch einmal
            hinzu.
          </p>
        </div>
        <div>
          <span class="block font-bold mb-2"
            >Falls du einen Proxyserver verwendest…</span
          >
          <p class="text-[#777777]">
            Vergewissere dich, dass der Proxyserver funktioniert. Überprüfe die
            Proxyeinstellungen oder wende dich an deinen Netzwerkadministrator.
            Falls du keinen Proxyserver verwenden möchtest, deaktiviere ihn wie
            folgt: Gehe zu „Programme“ > „Systemeinstellungen“ > „Netzwerk“ >
            „Erweitert“ > „Proxys“ und deaktiviere alle ausgewählten
            Proxyserver.
          </p>
        </div>
      </div>
    {/if}
  </div>
</div>
