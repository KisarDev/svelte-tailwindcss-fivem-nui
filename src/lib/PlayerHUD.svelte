<script>
    const jogador = {
        vida: 30,
        colete: 50,
        inventario: {
            armas: [
                { nome: "Pistola", dano: 10, id:1 },
                { nome: "Faca", dano: 20, id:2 }
            ],
        },
        armaAtiva: { id: 1, municao:4 },
    }

    const tabelaDeLider = {
        jogadores: [
            { nome: "Floki", pontos: 300, posicao: 1 },
            { nome: "Rodrigues", pontos: 200, posicao: 2 },
            { nome: "Sampaio", pontos: 150, posicao: 3 },
            { nome: "Kant", pontos: 200, posicao: 4 },
            { nome: "MartinzDev", pontos: 150, posicao: 20 }
        ]
    };

    // Ordena os jogadores por posição (ou pontuação, se preferir)
    $: jogadoresOrdenados = [...tabelaDeLider.jogadores].sort((a, b) => a.posicao - b.posicao);

    const tabelaDeMorte = [
        { jogadorQueMatou: "MartinzDev", jogadorQueMorreu: "Floki", arma: "Pistola" },
        { jogadorQueMatou: "Rodrigues", jogadorQueMorreu: "Sampaio", arma: "Faca" },
        { jogadorQueMatou: "Kant", jogadorQueMorreu: "Floki", arma: "Pistola" },
        { jogadorQueMatou: "Floki", jogadorQueMorreu: "Rodrigues", arma: "Faca" },
        { jogadorQueMatou: "Sampaio", jogadorQueMorreu: "Kant", arma: "Pistola" }
    ]
</script>

<div class="w-full h-full flex HUD">
    <div class="absolute top-[30px] left-[30px] tabelaDeLider">
        {#each jogadoresOrdenados as jogador, index}
            <div class="flex justify-between items-center bg-gradient-to-r from-[#0F0E0A] to-[#0F0E0A]/0 p-2 m-1 font-bold gap-2 border-l-2">
                <span>{jogador.posicao}</span>
                <span>{jogador.nome}</span>
                <span>{jogador.pontos}</span>
            </div>
        {/each}

    </div>


    <div class="absolute top-[30px] right-[30px] tabelaDeMorte">
        {#each tabelaDeMorte as morte, index}
            <div class="flex justify-between items-center bg-gray-800 p-2 m-1 rounded gap-2 ">
                <span>{morte.jogadorQueMatou}</span>
                <span>{morte.arma}</span>
                <span>{morte.jogadorQueMorreu}</span>
            </div>
        {/each}

    </div>

    <div class="absolute bottom-[30px] left-[30px]  p-4 rounded flex flex-col w-[200px]">
        <div class="flex flex-row justify-center items-center gap-2">
            <h2 class="text-lg font-bold ">{jogador.vida}</h2>
            <div class="w-full h-4 bg-[#727272] overflow-hidden">
            <div
                class="h-full bg-[#FF5252] transition-all duration-300"
                style="width: {jogador.vida}%"
            ></div>
            </div>
        </div>
        <div class="flex flex-row justify-center items-center gap-2">
            <h2 class="text-lg font-bold ">{jogador.colete}</h2>
            <div class="w-full h-4 bg-[#727272] overflow-hidden">
            <div
                class="h-full bg-[#FFFFFF] transition-all duration-300"
                style="width: {jogador.colete}%"
            ></div>
            </div>
        </div>
      </div>

    <div class="absolute bottom-[30px] right-[30px] inventario">
        <div class="flex flex-col gap-2 bg-gray-800 p-2 rounded">
            <h1 class="text-xl">Inventário</h1>
            {#each jogador.inventario.armas as arma, index}
                <div class="flex justify-between items-center bg-gray-700 p-2 m-1 rounded gap-2 ">
                    <span>{arma.nome}</span>
                    <span>{arma.dano}</span>
                </div>
            {/each}
        </div>

    </div>
</div>