<script lang="ts">
  let host = window.location.host;
</script>

<div
  class="bg-white dark:bg-[#1c1b22] w-screen h-screen grid place-items-center px-10 xs:px-20"
>
  <div
    class="max-w-[48rem] text-[#15141a] dark:text-[#fbfbfe] flex flex-col text-md gap-8 mt-8"
  >
    <h1 class="text-3xl xs:text-[2rem] font-thin ">
      Seite wurde nicht gefunden
    </h1>
    <p>Die Verbindung mit dem Server {host} schlug fehl.</p>
    <div>
      <p class="font-bold">
        Falls die Adresse korrekt ist, können Sie noch Folgendes versuchen:
      </p>
      <ul class="list-disc ml-8 mt-2 text-sm">
        <li class="my-2">Die Seite später noch einmal aufrufen.</li>
        <li class="my-2">Die Netzwerkverbindung überprüfen.</li>
        <li class="my-2">
          Falls der Computer sich hinter einer Firewall befindet, überprüfen Sie
          bitte, ob Firefox der Internetzugriff erlaubt wurde.
        </li>
      </ul>
    </div>
    <div class="flex justify-end">
      <button
        tabindex="-1"
        class="bg-[#0061e0] dark:bg-[#00ddff] text-[#fbfbfe] dark:text-[#15141a] hover:bg-[#0250bb] dark:hover:bg-[#80ebff]
        py-1 px-6 font-semibold rounded-[0.25rem] cursor-default w-full xs:w-fit"
        on:click={() => window.location.reload()}>Nochmals versuchen</button
      >
    </div>
  </div>
</div>
