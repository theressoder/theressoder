<script>
    const profileImg = '/profile.jpg';
</script>

<!-- HERO -->
<section class="bg-oat py-16 px-6 flex flex-col-reverse md:flex-row items-center md:justify-center gap-12">
    <!-- Text -->
    <div class="text-center md:text-left max-w-lg">
        <h2 class="mb-4">Hej, Theres Söder här!</h2>
        <p class="text-slate text-lg mb-2">
            Frontendutvecklare.
        </p>
        <p class="text-slate text-lg mb-2">
            Legitimerad gymnasielärare.
        </p>
        <p class="text-slate text-lg mb-8">
            Hälsoinspiratör.
        </p>
        <p class="text-slate text-lg mb-2">
            Jag bygger gränssnitt som inspirerar – och gör det svåra enkelt.
        </p>
        <p class="text-slate text-lg mb-8">
            Framgång är resultatet av små, konsekventa handlingar.
        </p>
        <div class="space-x-4">
            <a href="#projects"
                class="bg-transparent border-2 border-moss text-moss font-bold px-6 py-3 rounded-full 
                hover:bg-moss hover:text-oat transition-colors">
                Mina projekt
            </a>
            <a href="#contact"
                class="bg-transparent border-2 border-moss text-moss font-bold px-6 py-3 rounded-full 
                    hover:bg-moss hover:text-oat transition-colors">
                Kontakta mig
            </a>
        </div>
    </div>

    <!-- Bild -->
    <div class="w-48 h-48 md:w-64 md:h-64 rounded-full overflow-hidden border-4 border-slate 
              shadow-[8px_8px_0_0_var(--tw-shadow-color)] shadow-moss">
        <img src={profileImg} alt="Profilbild" class="w-full h-full object-cover object-[center_30%]" />
    </div>
</section>

<!-- ABOUT -->
<section id="about" class="bg-stone py-20 px-6 text-center border-t-2 border-b-2 border-slate md:text-left md:px-20">
    <h2 class="mb-6">Om mig</h2>
    <p class="text-slate max-w-2xl mx-auto mb-2 md:mx-0 leading-relaxed">
        Jag har jobbat som gymnasielärare i 15 år innan jag bytte bana till frontendutveckling. 
        Pedagogiken har gett mig verktygen att på ett unikt sätt förklara komplexa idéer och bygga användarvänliga lösningar.  
        Idag kombinerar jag min känsla för struktur och lärande med en passion för kod och design.
        Jag driver även en verksamhet som hälsoinspiratör där jag hjälper människor att hitta balans i livet genom kost, träning och mental hälsa.
    </p>
    <p class="text-slate max-w-2xl mx-auto md:mx-0 leading-relaxed">
        Utanför arbetet är jag en kreativ person som löptränar för att rensa huvudet och väcka nya idéer. 
        Jag uppskattar också handarbete, framför allt stickning och virkning, som ger mig en avkopplande och närvarande motvikt till allt skärmjobb. 
        Den här balansen mellan fysisk aktivitet, natur och hantverk formar mitt sätt att arbeta och leva — enkelhet, fokus och kreativitet.
    </p>
    
</section>

<!-- PROJECTS -->
<section id="projects" class="bg-oat py-20 px-6">
    <h2 class="text-center mb-12">Mina projekt</h2>
    <div class="grid gap-8 md:grid-cols-3 max-w-6xl mx-auto">
        <div class="bg-oat border-2 border-slate rounded-lg p-6 text-center 
                    shadow-[6px_6px_0_0_var(--tw-shadow-color)] shadow-moss">
            <h3 class="mb-2">Frontendutvecklare</h3>
            <p class="text-slate mb-4">Användarvänlighet och visuellt tilltalande gränssnitt.</p>
            <a href="/developer" class="text-clay font-bold hover:underline">Visa mer →</a>
        </div>

        <div class="bg-oat border-2 border-slate rounded-lg p-6 text-center 
                    shadow-[6px_6px_0_0_var(--tw-shadow-color)] shadow-moss">
            <h3 class="mb-2">Gymnasielärare</h3>
            <p class="text-slate mb-4">Matematik, fysik, programmering, webbutveckling och teknik.</p>
            <a href="/teacher" class="text-clay font-bold hover:underline">Visa mer →</a>
        </div>

        <div class="bg-oat border-2 border-slate rounded-lg p-6 text-center 
                    shadow-[6px_6px_0_0_var(--tw-shadow-color)] shadow-moss">
            <h3 class="mb-2">Hälsoinspiratör</h3>
            <p class="text-slate mb-4">Inspirerar till förändring i livet och löpning i balans.</p>
            <a href="/inspirer" class="text-clay font-bold hover:underline">Visa mer →</a>
        </div>
    </div>
</section>