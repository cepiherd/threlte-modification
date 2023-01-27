<script>
	import { AmbientLight, DirectionalLight, Mesh } from "@threlte/core";
	import { AutoColliders, CollisionGroups } from "@threlte/rapier";
	import {
		BoxBufferGeometry,
		MeshStandardMaterial,
		MeshBasicMaterial,
	} from "three";
	import { HTML } from "@threlte/extras";
	import Door from "./Door.svelte";
	import Player from "./Character.svelte";
	import Soldier from "./Soldier.svelte";
	import Job from "./Job.svelte";
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
	<Player />
	<Soldier />
	<Job />

	/>
	<!-- <Door /> -->
	<AutoColliders shape={"cuboid"}>
		<Soldier />
	</AutoColliders>
	<!-- WALLS -->
	<AutoColliders shape={"cuboid"}>
		<Mesh
			position={{ y: 1, x:2 ,z:3}}
			geometry={new BoxBufferGeometry(1, 3, 1)}
			material={new MeshStandardMaterial({
				transparent: false,
				// opacity: 0.5,
				color: 0xed872d,
			})}/>


<Mesh
			position={{ y: 1, x:5 ,z:3}}
			geometry={new BoxBufferGeometry(2, 2, 4)}
			material={new MeshStandardMaterial({
				transparent: false,
				// opacity: 0.5,
				color: 0xed872d,
			})}/>
		
		

	
	</AutoColliders>
</CollisionGroups>

<style>
	p {
		color: white;
		font-weight: bold;
	}
</style>
