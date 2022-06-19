<script context='module'>
    export async function load({params}) {
        const id = params.id;
        const url = `https://pokeapi.co/api/v2/pokemon/${id}`;
        const res = await fetch(url);
        const pokemon = await res.json();
        return {props: {pokemon}};
    }
</script>
<script>
    export let pokemon;
    const type = pokemon.types[0].type.name;
</script>

<div class='flex flex-col items-center'>
    <h1 class='text-4xl text-center my-8 uppercase'>{pokemon.name}</h1>
    <p>Type: <strong>{type}</strong> | Height: <strong>{pokemon.height}</strong>
        | Weight: <strong>{pokemon.weight}</strong>
    </p>
    <img class='card-image' src={pokemon.sprites['front_default']}
         alt={pokemon.name}
    />
</div>
