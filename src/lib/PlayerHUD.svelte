<script>
    const jogador = {
        vida: 100,
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
    }
    const tabelaDeMorte = [
        { jogadorQueMatou: "MartinzDev", jogadorQueMorreu: "Floki", arma: "Pistola" },
        { jogadorQueMatou: "Rodrigues", jogadorQueMorreu: "Sampaio", arma: "Faca" },
        { jogadorQueMatou: "Kant", jogadorQueMorreu: "Floki", arma: "Pistola" },
        { jogadorQueMatou: "Floki", jogadorQueMorreu: "Rodrigues", arma: "Faca" },
        { jogadorQueMatou: "Sampaio", jogadorQueMorreu: "Kant", arma: "Pistola" }
    ]
</script>

<div class="w-full h-full flex">
    <div>
        {#each tabelaDeLider.jogadores as jogador, index}
            <div class="flex justify-between items-center bg-gray-800 p-2 m-1 rounded">
                <span>{jogador.posicao}</span>
                <span>{jogador.nome}</span>
                <span>{jogador.pontos}</span>
            </div>
        {/each}

    </div>
</div>