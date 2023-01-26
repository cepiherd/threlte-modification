<script>
	import { AmbientLight, DirectionalLight, Mesh } from "@threlte/core";
	import { AutoColliders, CollisionGroups } from "@threlte/rapier";
	import { BoxBufferGeometry, MeshStandardMaterial } from "three";
	import { HTML } from "@threlte/extras";
	import Door from "./Door.svelte";
	import Player from "./Character.svelte";
    import Soldier from "./Soldier.svelte";
</script>

<DirectionalLight shadow position={{ y: 20, x: 8, z: -3 }} />
<AmbientLight intensity={0.2} />
<CollisionGroups groups={[0, 15]}>
	<AutoColliders shape={"cuboid"} position={{ y: -0.5 }}>
		<Mesh
			receiveShadow
			geometry={new BoxBufferGeometry(100, 1, 100)}
			material={new MeshStandardMaterial()}
		/>
	</AutoColliders>
</CollisionGroups>
<CollisionGroups groups={[0]}>
	<!-- position={{ x: 2 }} -->
	<Soldier />
	<Player />
	<!-- <Door /> -->
	<AutoColliders shape={"cuboid"}>
		<Mesh
			receiveShadow
			castShadow
			position={{ y: 0, x: +0.7 + 0.15, z: 15.2 }}
			geometry={new BoxBufferGeometry(2, 0.2, 2.15)}
			material={new MeshStandardMaterial({
				transparent: true,
				// opacity: 0.5,
				color: 0x333333,
			})}
		/>s
		<Mesh
			receiveShadow
			castShadow
			position={{ y: 1.75, x: +0.7 + 0.15, z: 10.2 }}
			geometry={new BoxBufferGeometry(10, 2.55, 2.15)}
			material={new MeshStandardMaterial({
				transparent: true,
				// opacity: 0.5,
				color: 0x333333,
			})}
		/>
	</AutoColliders>
	<!-- WALLS -->
	<!-- <AutoColliders shape={"cuboid"}>
		<Mesh
			receiveShadow
			castShadow
			position={{ y: 1.275, x: 30 + 0.7 + 0.15 }}
			geometry={new BoxBufferGeometry(60, 2.55, 0.15)}
			material={new MeshStandardMaterial({
				transparent: true,
				opacity: 0.5,
				color: 0x333333,
			})}
		/>
		<Mesh
			receiveShadow
			castShadow
			position={{ y: 1.275, x: -30 - 0.7 - 0.15 }}
			geometry={new BoxBufferGeometry(60, 2.55, 0.15)}
			material={new MeshStandardMaterial({
				transparent: true,
				opacity: 0.5,
				color: 0x333333,
			})}
		/>
	</AutoColliders> -->
</CollisionGroups>

<style>
	p {
		color: white;
		font-weight: bold;
	}
</style>
