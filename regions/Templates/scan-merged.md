# GameObjects Merged Scan - All Packs
# Total nodes: 25528
# Total types: 20
# Packs: gustav shared gustavdev shareddev honour 

## Pack Summary

| Pack | Nodes | Types | Unique Attrs |
|------|-------|-------|-------------|
| gustav | 1252 | 13 | 273 |
| shared | 15188 | 20 | 415 |
| gustavdev | 3072 | 11 | 252 |
| shareddev | 6006 | 12 | 310 |
| honour | 10 | 2 | 63 |
| **MERGED** | **25528** | **20** | **443** |

## Type Summary

| Type | Total Nodes | Unique Attrs |
|------|-------------|-------------|
| scenery | 10249 | 49 |
| item | 9325 | 150 |
| character | 2454 | 136 |
| prefab | 820 | 17 |
| TileConstruction | 579 | 15 |
| LevelTemplate | 561 | 36 |
| projectile | 480 | 64 |
| light | 446 | 50 |
| decal | 349 | 23 |
| surface | 87 | 43 |
| CombinedLight | 76 | 51 |
| trigger | 42 | 86 |
| Schematic | 40 | 13 |
| fogVolume | 7 | 27 |
| SplineConstruction | 5 | 13 |
| Spline | 3 | 21 |
| lightProbe | 2 | 27 |
| constellationHelper | 1 | 15 |
| constellation | 1 | 14 |
| terrain | 1 | 12 |

## ALL UNIQUE ATTRIBUTES (443 total)

| Attribute | Type | Total Count | In Types | Packs | Examples |
|-----------|------|-------------|----------|-------|----------|
| `_OriginalFileVersion_` | int64 | 25528 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | 144678138029277484 / 144115207403209022 / 144115207403209026 |
| `Acceleration` | float | 213 | projectile | gustav, gustavdev, shared, shareddev | 7 / 50 / 35 |
| `ActivationGroupId` | FixedString | 8 | character, item | gustav, gustavdev, shared | IRN_Countdown / b78fda61-ffd1-4898-b518-48ed025ac299 / 58ef640d-6bdf-4acc-86ab-ff0f21317af2 |
| `ActiveCharacterLightID` | FixedString | 54 | character | gustav, gustavdev, shared, shareddev | 233033a1-b43a-4ad9-976a-8a062b345e21 / 3f14f857-bd0f-4538-b059-9b18fb9af723 / e278f6a0-26d7-49be-b11a-9b84bc313c3c |
| `AiHint` | guid | 562 | character, item | gustav, gustavdev, honour, shared, shareddev | 45a231e4-e94f-4b0e-a941-2daf1adf44b5 / f76e60e1-2957-470b-8a25-efdf32475ce0 / f5614548-32cc-4e2e-b108-32e5d532471e |
| `AiPathColor` | fvec3 | 52 | surface | shared, shareddev | 0 1 1 / 1 1 0 |
| `AiUseCombatHelper` | FixedString | 1 | item | gustavdev | Projectile_COL_AiHelper_UseItem_NecromancerCandle |
| `Albedo` | fvec3 | 7 | fogVolume | gustavdev, shared | 0.78431374 0.84705883 0.95686275 / 0.2 0.12941177 0.37254903 / 1 1 1 |
| `AliveInventoryType` | uint8 | 4 | character | gustavdev, shared, shareddev | 0 / 41 |
| `AllowCameraMovement` | bool | 64 | scenery | shared | True / False |
| `AllowSummonGenericUse` | bool | 19 | item | shared, shareddev | True |
| `AllowSummonTeleport` | bool | 4 | item | gustav, shared | True / False |
| `AlwaysUseDefaultLifeTime` | bool | 3 | surface | shared | True |
| `AmbientSound` | FixedString | 1 | trigger | shared | 00000000-0000-0000-0000-000000000000 |
| `Amount` | int32 | 10 | item | gustavdev, shared | 2 / 100 / 1 |
| `Amount` | float | 256 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 3000 / 0.5 / 1 |
| `Angle` | float | 2 | trigger | shared | -1 |
| `Angle` | fvec2 | 270 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 1 90.41 / 35 45 / 20 20 |
| `AngleCutoff` | float | 243 | decal | gustav, shared, shareddev | 0.8 / 0 |
| `AnimationSetResourceID` | FixedString | 146 | character | gustav, gustavdev, shared, shareddev | ae996c12-9f93-655f-6f04-f7bec8cef6eb / bbf6ee33-3328-946a-9b9f-872f0624e15d / 51c6e8a6-14a0-d68d-cf3d-22ee6ccc31ef |
| `AnubisConfigName` | FixedString | 610 | character, item | gustav, gustavdev, honour, shared, shareddev | WYR_WyrmRock_GortashShieldCapacitor_Broken / WYR_Circus_Thug_02 / DefaultMonster |
| `Archetype` | FixedString | 948 | character, item | gustav, gustavdev, honour, shared, shareddev | goblin_mage / act2_TWN_surgeon / act3_LOW_ghost_nurse |
| `AreaLevelOverrideGuid` | guid | 1 | trigger | shared | 00000000-0000-0000-0000-000000000000 |
| `AttackableWhenClickThrough` | bool | 216 | item | gustav, gustavdev, shared, shareddev | False / True |
| `AttenuationScale` | float | 1 | trigger | shared | 1 |
| `AuxBus1` | uint8 | 1 | trigger | shared | 0 |
| `AuxBus2` | uint8 | 1 | trigger | shared | 0 |
| `AuxBus3` | uint8 | 1 | trigger | shared | 0 |
| `AuxBus4` | uint8 | 1 | trigger | shared | 0 |
| `AvoidTraps` | bool | 3 | character | shared, shareddev | True / False |
| `BeamFX` | FixedString | 42 | projectile | shared, shareddev | VFX_Beams_Poison_PoisonSpray_Beam_01 / VFX_Projectiles_ChillOfTheMountain_Beam_01 / VFX_Spells_Cast_Warlock_ProjectileBeam_EldritchBlast_Beam_01 |
| `BlockAoEDamage` | bool | 4 | item | shareddev | True / False |
| `BloodSurfaceType` | FixedString | 430 | character, item | gustav, gustavdev, honour, shared, shareddev | SurfaceBloodSilver / SurfaceOil / SurfaceBlood |
| `BloodType` | FixedString | 154 | character, item | gustav, gustavdev, honour, shared, shareddev | Red / Mithral / Fire |
| `BookType` | uint8 | 136 | item | gustav, gustavdev, shared, shareddev | 7 / 3 / 1 |
| `Border` | float | 1 | trigger | gustav | 0.5 |
| `CameraOffset` | fvec3 | 3268 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | 0 0 0 |
| `CanBeImprovisedWeapon` | bool | 164 | item | gustav, gustavdev, shared, shareddev | False / True |
| `CanBeMoved` | bool | 330 | item | gustav, gustavdev, shared, shareddev | False / True |
| `CanBePickedUp` | bool | 348 | character, item | gustav, gustavdev, honour, shared, shareddev | False / True |
| `CanBePickpocketed` | bool | 28 | item | gustavdev, shared, shareddev | False |
| `CanBeTeleported` | bool | 47 | character | gustav, gustavdev, shared, shareddev | False / True |
| `CanClickThrough` | bool | 2359 | item, scenery | gustav, gustavdev, shared, shareddev | False / True |
| `CanClimbLadders` | bool | 85 | character | gustav, gustavdev, shared, shareddev | False / True |
| `CanClimbOn` | bool | 2822 | item, scenery | gustav, gustavdev, shared, shareddev | False / True |
| `CanConsumeItems` | bool | 6 | character | gustavdev, shared, shareddev | False |
| `CanEnterCombat` | bool | 5 | surface | shared | True / False |
| `CanFight` | bool | 110 | character, item | gustav, gustavdev, shared, shareddev | False / True |
| `CanJoinCombat` | bool | 170 | character, item | gustav, gustavdev, shared, shareddev | False / True |
| `CanOpenDoors` | bool | 39 | character | gustav, gustavdev, shared, shareddev | False / True |
| `CanSeeThrough` | bool | 2 | surface | shared | False |
| `CanShineThrough` | bool | 369 | item, scenery | gustavdev, shared, shareddev | True |
| `CanShootThrough` | bool | 3596 | character, item, scenery, surface | gustav, gustavdev, shared, shareddev | False / True |
| `CanWalkThroughDoors` | bool | 1 | character | gustavdev | True |
| `CaptureType` | uint8 | 2 | lightProbe | gustav, shared | 2 |
| `CastBone` | FixedString | 269 | projectile | gustav, gustavdev, shared, shareddev | Cast_FX / Dummy_FX / Dummy_CastFX |
| `CastShadow` | bool | 944 | character, CombinedLight, constellationHelper, item, light, lightProbe, prefab, projectile, scenery, surface, trigger | gustav, gustavdev, shared, shareddev | False / True |
| `CharacterVisualResourceID` | FixedString | 1757 | character | gustav, gustavdev, honour, shared, shareddev | 9cbd1f0e-fb2b-e7e1-c244-7a39dd325267 / f47d12e3-6f9d-4c2f-ab48-a1636a5c3d86 / 40beced7-8472-bc99-6e2c-009cf9a6d452 |
| `CinematicArenaFlags` | uint32 | 11 | item | gustavdev, shared, shareddev | 2 / 0 / 1 |
| `CollideWithCamera` | bool | 24 | scenery | shared | True / False |
| `Color` | fvec3 | 329 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 0.45882353 0.62352943 0.23921569 / 0.73333335 0.69411767 1 / 1 0.9411765 0.8627451 |
| `Color4` | fvec4 | 39 | trigger | gustav, shared, shareddev | 0.5 0 1 1 / 0.5 0 1 0 / 0.19607843 1 1 0.49803922 |
| `ColorPreset` | guid | 44 | item | gustav, gustavdev, shared, shareddev | 7c8ae356-9720-d6b2-02e6-70479f45adec / 428e99ed-6fd8-c81a-d856-be32f8d2df84 / 4157e913-f20d-037e-db5c-33a38d2b1e81 |
| `CombatGroupID` | FixedString | 26 | character | gustav, gustavdev, honour, shared, shareddev | adeb0032-c198-54c1-e4a5-5bc87e6f261a / b8945d7f-7a8d-ab9a-0a47-63b124322028 / f58d4687-56bb-4441-a20c-e234f776021b |
| `CombatName` | LSString | 4 | character, item | gustav, shareddev | S_GOB_Checkpoint_Goblin_Melee_01 / WPN_HUM_Sceptre_Karsus_A / S_FOR_Gnome_Goblin_Melee_01 |
| `ConstellationConfigName` | FixedString | 99 | item, LevelTemplate | gustav, gustavdev, shared, shareddev | VFXDoor / FallingStalactite / Mine |
| `ContainerAutoAddOnPickup` | bool | 5 | item | shared, shareddev | True / False |
| `ContainerContentFilterCondition` | LSString | 4 | item | shared | Tagged('BOOK') and not Tagged('SCROLL') / Tagged('KEY') / Tagged('ALCH_INGREDIENT') or Tagged('ALCH_EXTRACT') |
| `CoverAmount` | uint8 | 4984 | item, scenery | gustav, gustavdev, shared, shareddev | 1 / 0 |
| `CriticalHitType` | FixedString | 33 | character | gustav, gustavdev, honour, shared, shareddev | Default |
| `CrowdAreItemsAllowed` | bool | 1 | trigger | shared | False |
| `CrowdSystemEnabled` | bool | 1 | trigger | shared | False |
| `CurveResourceId` | FixedString | 18 | projectile | shared, shareddev | 291d60bc-a8cc-c032-29c5-529600be8950 / 1c29c693-15dc-5fe9-7092-85b8110e7f19 / 8c63aadf-ff7f-a545-053c-f53d78e262ac |
| `CustomMixRadius` | int16 | 1 | trigger | shared | -1 |
| `CustomPointTransform` | mat4x4 | 16 | trigger | gustav, shared, shareddev | 1.00  0.00  0.00  0.00 &#xD;&#xA; 0.00  1.00  0.00  0.00 &#xD;&#xA; 0.00  0.00  1.00  0.00 &#xD;&#xA; 0.00  0.00  0.00  1.00 &#xD;&#xA; |
| `DeathEffect` | guid | 141 | character | gustav, gustavdev, honour, shared, shareddev | 864da2c0-3cd2-4fc4-8353-19d628d9e550 / eb0aa43b-fcdc-4ef2-8c54-f60e75074e83 / 75329f47-87fc-4498-9612-833503daa22c |
| `DeathRaycastMaxLength` | float | 63 | character | gustav, gustavdev, honour, shared, shareddev | 1.5 / 1 |
| `DeathRaycastMinLength` | float | 26 | character | gustavdev, honour, shared, shareddev | 0.4 / 1 / 0 |
| `DeathRaycastVerticalLength` | float | 1 | character | shareddev | -2.5 |
| `DecalMaterial` | FixedString | 76 | surface | shared, shareddev | c6f40216-e19f-baac-b154-9e5ef4f5cb03 / f4aba39f-a3ca-4bbd-7df7-726966870e4e / 656e2b9c-4563-0d8d-af6f-6a00f353908f |
| `DecalType` | uint8 | 43 | decal | shared | 1 |
| `DefaultDialog` | FixedString | 1 | character | shared | 70f76b90-009e-b95a-0e76-65cc8eff73d3 |
| `DefaultLifeTime` | float | 12 | surface | shared | 1 / 12 / 600 |
| `DefaultState` | uint8 | 4 | character | gustav, shared, shareddev | 0 / 12 / 11 |
| `DefaultState` | FixedString | 29 | item | gustav, shared, shareddev | Hidden / idle / open |
| `Density` | float | 7 | fogVolume | gustavdev, shared | 0.01 / 0.04 / 0.005 |
| `Destroyed` | bool | 106 | item | gustav, shared, shareddev | False / True |
| `DestroyTrailFXOnImpact` | bool | 46 | projectile | shared, shareddev | False / True |
| `DestroyWithStack` | bool | 110 | item | shared, shareddev | True / False |
| `DetachBeam` | bool | 77 | projectile | gustav, gustavdev, shared, shareddev | True / False |
| `DevComment` | LSString | 75 | character, constellation, fogVolume, item, light, prefab, projectile, Spline | gustav, gustavdev, shared, shareddev | Root template repalcement for S_GLO_GnomePrisoner_002 in Act3 (WYR and futher): removes bruises, blood, dirt, etc. Also changes clothes and treasures. / |Gauth Eye Slime| / Steelwatch foundry - key from 2 Metal Crates. |
| `Dimensions` | fvec3 | 345 | decal | gustav, shared, shareddev | 0.5 1 1.4 / 1.5 0.1 1.5 / 1 1 1 |
| `DirectionLightAttenuationEnd` | float | 238 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 5 / 2.5 / 1 |
| `DirectionLightAttenuationFunction` | uint8 | 175 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 2 / 1 / 3 |
| `DirectionLightAttenuationSide` | float | 240 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 1.1 / 0.5 / 0.7 |
| `DirectionLightAttenuationStart` | float | 226 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 4 / 0.5 / 0.2 |
| `DirectionLightDimensions` | fvec3 | 249 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 4 3.5 3 / 1.2 1.2 1.8 / 8 8 16.5 |
| `DisableEquipping` | bool | 27 | character | gustav, gustavdev, shared, shareddev | True |
| `DisarmDC` | int32 | 5 | item | shared | -1 / 10 |
| `DisarmDifficultyClassID` | guid | 30 | item | gustav, gustavdev, shared, shareddev | fa621d38-6f83-4e42-a55c-6aa651a75d46 / 831e1fbe-428d-4f4d-bd17-4206d6efea35 / 5028066b-6ea0-4a6a-9e3e-53bee62559a7 |
| `DisarmDifficultyClassID` | int32 | 3 | item | shared | 30 |
| `DisintegratedResourceID` | FixedString | 91 | character | gustav, gustavdev, honour, shared, shareddev | a8df0d5a-d171-89d2-fd37-424a7f914ec6 / ab98118f-36e4-8a5f-2e91-925e1c9934c2 / c201a86a-297f-4d0d-16a3-073c1098767b |
| `DistanceMax_Bezier3` | float | 12 | projectile | shared, shareddev | 30 / 70 / 40 |
| `DistanceMax_Bezier4` | float | 3 | projectile | shareddev | 36 |
| `DistanceMin_Bezier3` | float | 12 | projectile | shared, shareddev | 0.1 / 6 / 1 |
| `DistanceMin_Bezier4` | float | 3 | projectile | shareddev | 3 |
| `DropSound` | FixedString | 367 | item | gustav, gustavdev, shared, shareddev | 8891f42c-f66e-b87a-d0b7-6f2de68489a8 / 2953d61b-cc69-557e-5c5e-2d626fab3d4c / fef7023c-75c1-6d74-0668-4e5ab2eb59e4 |
| `Enabled` | bool | 258 | CombinedLight, fogVolume, light, lightProbe | gustav, gustavdev, shared, shareddev | False / True |
| `EnableLightSpawning` | bool | 7 | surface | shared | True |
| `Equipment` | FixedString | 444 | character | gustav, gustavdev, honour, shared, shareddev | EQP_Spear / EQP_Club / EQP_Dagger_Leather_DW |
| `EquipmentRace` | guid | 214 | character | gustav, gustavdev, honour, shared, shareddev | 06aaae02-bb9e-4fa3-ac00-b08e13a5b0fa / e39505f7-f576-4e70-a99e-8e29cd381a11 / 7d73f501-f65e-46af-a13b-2cacf3985d05 |
| `EquipmentTypeID` | guid | 301 | item | gustav, gustavdev, shared, shareddev | 12b80df8-aaf1-4543-84fa-c44622e451b5 / 08d178fa-97a1-421c-987f-ec8093405b7c / 8ac2eb82-8563-4657-8c4c-1507573978d7 |
| `EquipSound` | FixedString | 65 | item | gustav, gustavdev, shared, shareddev | 75f7e7c8-e729-815f-ecd5-cc8d279ea5b4 / 92550df7-e13e-4474-8a7e-a59825eaa805 / 8891f42c-f66e-b87a-d0b7-6f2de68489a8 |
| `EventSendingMode` | uint8 | 3 | trigger | gustavdev, shared | 2 |
| `ExamineRotation` | fvec3 | 211 | item | gustav, gustavdev, shared, shareddev | 75 180 0 / 65 18 0 / -15 0 0 |
| `ExplodedResourceID` | FixedString | 106 | character | gustav, gustavdev, honour, shared, shareddev | 9b371eaa-2ebe-028e-d577-2202ab7acff1 / 3dd938ff-cd2f-797b-459a-6f3113a96bfa / 00000000-0000-0000-0000-000000000000 |
| `ExplorationReward` | guid | 1 | trigger | shared | 4c4c1c60-3362-4e84-84ad-ae1a140b17ee |
| `ExplosionFX` | FixedString | 4 | character | gustavdev, shared, shareddev | VFX_Enemies_Steelwatcher_Biped_SelfDestruct_Explosion_Impact_01 / VFX_Combat_Death_Explode_01 |
| `Extents` | fvec3 | 12 | trigger | gustav, shared | 50 50 50 / 0.5 0.5 0.5 / 1 1 1 |
| `Faction` | guid | 814 | character, item | gustav, gustavdev, honour, shared, shareddev | cfb709b3-220f-9682-bcfb-6f0d8837462e / 376e33c4-dd15-4c46-a586-87d8b421a0c7 / 64321d50-d516-b1b2-cfac-2eb773de1ff6 |
| `Fadeable` | bool | 785 | item, projectile, scenery, trigger | gustav, gustavdev, shared, shareddev | False / True |
| `FadeGroup` | FixedString | 2 | item, scenery | gustavdev, shared | BREW_SignPost_A / GNW_Roof_B |
| `FadeGroupOnly` | bool | 16 | trigger | gustav, shared, shareddev | False |
| `FadeIn` | bool | 197 | item, projectile, scenery | gustav, gustavdev, shared, shareddev | False / True |
| `FadeInSpeed` | float | 11 | surface | shared | 0.1 / 1 / 3 |
| `FadeOutSpeed` | float | 36 | surface | shared | 5 / 0.1 / 3 |
| `FadeTime` | float | 2 | trigger | shared | 4 |
| `FallDamageMultiplier` | float | 3 | surface | shared | 0 |
| `Flag` | int32 | 4510 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | 2 / 1 / 0 |
| `Flag` | uint8 | 91 | character, decal, item, LevelTemplate, light, prefab, projectile, scenery, surface, TileConstruction, trigger | gustav, gustavdev, shared, shareddev | 0 |
| `FlatFalloff` | bool | 270 | CombinedLight, light | gustav, gustavdev, shared, shareddev | False / True |
| `Floating` | bool | 1 | item | gustav | True |
| `FogVolumeShape` | uint8 | 7 | fogVolume | gustavdev, shared | 1 / 0 |
| `FoleyLongResourceID` | FixedString | 33 | character | gustav, gustavdev, shared, shareddev | 696a4d47-a4cc-cb2c-3c98-de94db8a697b / 63096ed3-12f4-4b82-bc89-2f57762d7b6f / 5b0220fb-ca10-d1ee-ea3e-1fd588b6a15d |
| `FoleyMediumResourceID` | FixedString | 43 | character | gustav, gustavdev, shared, shareddev | 696a4d47-a4cc-cb2c-3c98-de94db8a697b / f3bbd184-beb5-f1bc-e82d-454036b70aab / 783c4d60-f8c4-4458-a8e7-4d9e543b662e |
| `FoleyShortResourceID` | FixedString | 22 | character | gustav, shared, shareddev | 696a4d47-a4cc-cb2c-3c98-de94db8a697b / c71bc88b-d8e0-4eee-97a6-2eebb4affc5d / 686c7b4d-8de6-497d-a7ac-cfb6a6043c98 |
| `ForceAffectedByAura` | bool | 5 | item | gustavdev, shared, shareddev | False / True |
| `ForceLifetimeDeath` | bool | 41 | character | gustavdev, shared, shareddev | False / True |
| `FOV` | float | 4 | Spline, trigger | shared | 45 / 50 |
| `FreezeGravity` | bool | 49 | item | gustav, shared, shareddev | False / True |
| `Gain` | float | 315 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 3.5 / 0.15 / 0.05 |
| `GameplayCheckLOS` | bool | 68 | CombinedLight | gustav, shared, shareddev | False / True |
| `GameplayDirectionalDimensions` | fvec3 | 69 | CombinedLight | gustav, shared, shareddev | 8 8 15 / 3 3 5 / 2.5 2.5 15 |
| `GameplayEdgeSharpening` | float | 68 | CombinedLight | gustav, shared, shareddev | 0 |
| `GameplayIsActive` | bool | 68 | CombinedLight | gustav, shared, shareddev | True |
| `GameplayRadius` | float | 73 | CombinedLight | gustav, shared, shareddev | 12 / 3.5 / 10 |
| `GameplaySpotlightAngle` | float | 71 | CombinedLight | gustav, shared, shareddev | 13 / 20 / 33.795 |
| `GeneratePortrait` | LSString | 684 | character | gustav, gustavdev, honour, shared, shareddev | Icon_Sabertooth / Icon_Human_Male / Icon_Surgeon |
| `GenerateRunningDeepWater` | bool | 4 | scenery | shared | True / False |
| `GizmoColorOverride` | fvec4 | 24 | trigger | gustav, shared, shareddev | 0.5 0.5 0.5 0.5 / 1 0.85490197 0.57254905 0.9607843 / 0 0 0.25 1 |
| `GravityType` | uint8 | 575 | item | gustav, gustavdev, shared, shareddev | 2 / 1 / 0 |
| `GroundImpactFX` | LSString | 110 | projectile | gustavdev, shared, shareddev | VFX_Projectiles_Damage_Fire_FireBolt_Impact_Ground_01 / VFX_Combat_GroundImpact_Projectile_01 / VFX_Projectile_Arrow_Dispelling_GroundImpact_01 |
| `GroupID` | uint32 | 3300 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | 31045 / 7064 / 38088 |
| `GroupSizeMax` | uint16 | 1 | trigger | shareddev | 1 |
| `GroupSizeMin` | uint16 | 1 | trigger | shareddev | 1 |
| `GroupSpawnTimeMax` | float | 1 | trigger | shareddev | 1 |
| `GroupSpawnTimeMin` | float | 1 | trigger | shareddev | 1 |
| `HardcoreOnly` | bool | 6 | item | shared, shareddev | False / True |
| `HasCustomPoint` | bool | 19 | trigger | gustav, shared, shareddev | False |
| `HasGameplayValue` | bool | 3254 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, shared, shareddev | False / True |
| `Height` | float | 12 | trigger | shared | 2 |
| `HiddenFromMinimapRendering` | bool | 596 | item, LevelTemplate, scenery, TileConstruction | gustav, gustavdev, shared, shareddev | False / True |
| `HierarchyOnlyFade` | bool | 507 | item, scenery | gustav, gustavdev, shared, shareddev | False / True |
| `Hostile` | bool | 52 | item | gustav, gustavdev, shared, shareddev | False / True |
| `Icon` | FixedString | 7470 | character, item, scenery, surface | gustav, gustavdev, honour, shared, shareddev | Item_LOOT_Alchemy_Crystal_C / b3f8b133-b75e-810c-0f8d-9d1f37bee554-EQP_Warpick_Leather_(Icon_Human_Male) / Item_FUR_GEN_Painting_Gortash_A |
| `IgnoreGenerics` | bool | 17 | item | gustav, gustavdev, shared | False / True |
| `IgnoreRoof` | bool | 10 | projectile | shared, shareddev | False / True |
| `ImpactFX` | FixedString | 315 | projectile | gustav, gustavdev, shared, shareddev | VFX_Projectiles_Damage_Fire_ChromaticOrb_Impact_01 / VFX_Projectiles_SphereOfElementalBalance_Lightning_Impact_01 / VFX_Projectiles_Fireball_Impact_01 |
| `ImpactSound` | FixedString | 315 | item | gustav, gustavdev, shared, shareddev | d44f2631-ebea-49ff-79ba-415636e0270a / 439fcec3-6032-f489-6e80-260d26fab23d / fa6145a3-f95d-60a9-9583-ba601bc3a583 |
| `ImpactSoundResourceID` | FixedString | 64 | projectile | shared, shareddev | f3839eea-3f9c-4e77-bacf-29085a3c7d41 / 6e6cdb06-a4e7-49eb-b16b-626204a57935 / cf56c061-6788-469b-b7fe-ad1345ff08f4 |
| `Index` | uint8 | 4 | trigger | shared | 0 |
| `InfiniteCapture` | bool | 2 | lightProbe | gustav, shared | True |
| `InfluenceTreasureLevel` | bool | 1 | character | shared | False |
| `InitialSpeed` | float | 290 | projectile | gustav, gustavdev, shared, shareddev | 50 / 35 / 40 |
| `Intensity` | float | 430 | CombinedLight, light, lightProbe | gustav, gustavdev, shared, shareddev | 120000 / 3000 / 15000 |
| `InteractionFilterRequirement` | uint8 | 1 | item | shareddev | 1 |
| `InteractionFilterType` | uint8 | 68 | item | gustav, gustavdev, shared, shareddev | 2 / 1 |
| `InventoryMoveSound` | FixedString | 349 | item | gustav, gustavdev, shared, shareddev | 35db8b7d-69ee-868e-3201-d398f6c7d709 / 8891f42c-f66e-b87a-d0b7-6f2de68489a8 / 2953d61b-cc69-557e-5c5e-2d626fab3d4c |
| `InventoryType` | uint8 | 484 | character, item | gustav, gustavdev, honour, shared, shareddev | 7 / 9 / 35 |
| `IsAnchor` | bool | 1 | trigger | shared | False |
| `IsBlocker` | bool | 334 | item, scenery | shared, shareddev | False / True |
| `IsBlueprintDisabledByDefault` | bool | 50 | item | gustav, gustavdev, shared, shareddev | False / True |
| `IsBoss` | bool | 19 | character, item | gustav, gustavdev, honour, shared, shareddev | False / True |
| `IsCinematic` | bool | 80 | LevelTemplate | gustav, gustavdev, shared, shareddev | False / True |
| `IsDecorative` | bool | 140 | item, scenery | gustav, shared, shareddev | False / True |
| `IsDroppedOnDeath` | bool | 4 | item | gustavdev, shared, shareddev | False / True |
| `IsDynamicLayer` | bool | 471 | LevelTemplate | gustav, gustavdev, shared, shareddev | False |
| `IsEquipmentLootable` | bool | 112 | character | gustav, gustavdev, honour, shared, shareddev | False / True |
| `IsFlickering` | bool | 218 | CombinedLight, light | gustav, gustavdev, shared, shareddev | False / True |
| `IsForcedType` | bool | 19 | scenery | shared | True |
| `IsHalfLit` | bool | 68 | CombinedLight | gustav, shared, shareddev | False |
| `IsHuge` | bool | 1 | item | shared | False |
| `IsImprovisedWeapon` | bool | 1 | item | gustavdev | True |
| `IsInspector` | bool | 753 | character, item | gustav, gustavdev, shared, shareddev | False / True |
| `IsInteractionDisabled` | bool | 56 | item | gustav, gustavdev, shared, shareddev | False / True |
| `IsKey` | bool | 26 | item | gustavdev, shared, shareddev | False / True |
| `IsLootable` | bool | 145 | character | gustav, gustavdev, honour, shared, shareddev | False / True |
| `IsMoving` | bool | 719 | CombinedLight, LevelTemplate, light | gustav, gustavdev, shared, shareddev | False / True |
| `IsPlatformOwner` | bool | 8 | item | gustav, shared | True / False |
| `IsPlatformSpline` | bool | 2 | Spline | shared | True / False |
| `IsPlayer` | bool | 28 | character | gustavdev, shared, shareddev | False / True |
| `IsPointerBlocker` | bool | 1356 | item, scenery | gustav, gustavdev, shared, shareddev | False / True |
| `IsPortal` | bool | 214 | item | gustav, gustavdev, shared, shareddev | False |
| `IsPortalProhibitedToPlayers` | bool | 4 | item | gustav, shared | True / False |
| `IsPublicDomain` | bool | 160 | item | gustav, gustavdev, shared, shareddev | False / True |
| `IsRooof` | bool | 1 | trigger | gustav | False |
| `IsScrollingObject` | bool | 514 | LevelTemplate | gustav, gustavdev, shared, shareddev | False / True |
| `IsShadowProxy` | bool | 16 | item, LevelTemplate, scenery | gustavdev, shared, shareddev | False / True |
| `IsSimpleCharacter` | bool | 22 | character | shared, shareddev | True |
| `IsSourceContainer` | bool | 2 | item | shared, shareddev | True |
| `IsStraightPath` | bool | 1 | Spline | shared | True |
| `IsSunlight` | bool | 67 | CombinedLight | gustav, shared, shareddev | False / True |
| `IsSurfaceBlocker` | bool | 15 | item | gustav, gustavdev, shared, shareddev | False / True |
| `IsSurfaceCloudBlocker` | bool | 16 | item | gustav, gustavdev, shared | False / True |
| `IsTradable` | uint8 | 1 | character | gustavdev | 1 |
| `IsTrap` | bool | 40 | item | gustav, gustavdev, shared, shareddev | False / True |
| `IsUsingCalculatedSceneBounds` | bool | 1 | trigger | shared | True |
| `IsWorldTimeline` | bool | 1 | trigger | shared | False |
| `JumpUpLadders` | bool | 2 | character | shared, shareddev | True / False |
| `Kelvin` | float | 267 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 2600 / 6445.8965 / 6400 |
| `Key` | FixedString | 31 | item | gustav, gustavdev, shared | LOW_Key_DiabolicForge / LOW_SorcerousSundriesBasement_SideChest01 / Key_LOW_SteelwatchFoundry_MetalCrate |
| `LadderAttachOffset` | float | 70 | character | gustav, gustavdev, honour, shared, shareddev | 1.3 / 0.1 / 0 |
| `LadderAttachSpeed` | float | 5 | character | gustav, shared | 3 |
| `LadderDetachSpeed` | float | 5 | character | gustav, shared | 2.5 |
| `LadderLoopSpeed` | float | 143 | character | gustav, gustavdev, honour, shared, shareddev | 3 / 4.5 / 11.25 |
| `Layer` | uint32 | 327 | decal | gustav, shared, shareddev | 5 / 1 / 0 |
| `Layer` | int32 | 4 | fogVolume | gustavdev, shared | 1 / 0 |
| `LevelOverride` | int32 | 948 | character, item, trigger | gustav, gustavdev, honour, shared, shareddev | 7 / 9 / 3 |
| `LevelTemplateType` | uint8 | 482 | LevelTemplate | gustav, gustavdev, shared, shareddev | 2 / 1 / 0 |
| `LifeTime` | float | 33 | projectile | gustav, shared, shareddev | 1 / 20 / 15 |
| `LightChannel` | uint8 | 78 | character, item | gustav, gustavdev, honour, shared, shareddev | 5 / 24 / 0 |
| `LightChannelFlag` | uint8 | 206 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 161 / 159 / 32 |
| `LightCookieTexture` | FixedString | 20 | CombinedLight, light | shared | 64a115a5-a9a5-2ec1-cfe1-df49f3f34b21 / 9ca10249-a617-efb3-3a03-49757e36a4ca / aa836bc5-d24a-81a5-91a1-7b4a082884d0 |
| `LightID` | FixedString | 144 | character | gustav, gustavdev, shared, shareddev | 362270fc-bf6b-4603-bb8a-6deebbcca47b / b8299899-3785-42f2-aaf3-6c26445545b3 / 3faa1c66-5d35-4e87-868e-d124168b660f |
| `LightProbeShape` | uint8 | 2 | lightProbe | gustav, shared | 0 |
| `LightProbeType` | uint8 | 2 | lightProbe | gustav, shared | 1 |
| `LightType` | uint8 | 261 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 2 / 1 / 0 |
| `LightVolume` | bool | 16 | light | gustav, shared, shareddev | False / True |
| `LightVolumeSamplesCount` | int32 | 16 | light | gustav, shared, shareddev | 1024 |
| `LockDC` | int32 | 1 | item | shared | -1 |
| `LockDifficultyClassID` | guid | 1 | item | gustavdev | b9cea18d-f40a-444d-a692-76582a69130c |
| `Looping` | bool | 3 | Spline | shared | True |
| `LoopSound` | FixedString | 1312 | item, scenery | gustav, shared, shareddev | 356982d9-7084-58f8-a3aa-54b27585ee2d / 92182f4d-e6e8-1022-0ee2-8df5446bf303 / f2012727-03e9-c698-a3e9-d373538784d1 |
| `MapKey` | FixedString | 25528 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | 074b7826-cbc9-4cf4-b701-de362f659259 / 002827e6-8b00-42f4-b679-1e9b9140c23d / 00087155-70a0-405b-b59a-cceb0c7bccb0 |
| `MapMarkerStyle` | FixedString | 2 | item | shared | MagicMirror / WithersWardrobe |
| `Material` | FixedString | 346 | decal | gustav, shared, shareddev | aa15f525-d033-8e00-259a-d1b6bf7a1695 / be60ad10-3110-d12d-47af-dcb2177e3bb2 / 906c4613-889d-4043-2cac-9fa9760310b6 |
| `MaterialPreset` | guid | 1 | item | shared | f5fad36b-e70e-d401-aa2d-c8cc3b036b3b |
| `MaterialType` | uint8 | 46 | surface | shared, shareddev | 21 / 24 / 35 |
| `MaxAttenuation` | int16 | 1 | trigger | shared | -1 |
| `MaxCharacters` | uint16 | 1 | trigger | shareddev | 1 |
| `MaxPathRadius` | float | 2 | projectile | shared | 1 |
| `maxStackAmount` | int32 | 521 | item | gustav, gustavdev, shared, shareddev | 100 / 20 / 1 |
| `MeshProxy` | FixedString | 60 | item | gustav, shared | 00000000-0000-0000-0000-000000000000 / 3f38bcda-21ee-66bb-3c6d-be241a1df6f0 |
| `MixdownDelayTime` | float | 2 | trigger | shared | -1 |
| `MixdownSpeed` | uint8 | 2 | trigger | shared | 3 |
| `MovablePlatformStartSound` | FixedString | 431 | LevelTemplate | gustav, gustavdev, shared, shareddev | 85018e75-1504-9afc-f4b4-fe1a3210d329 / b2802ca6-a2ac-9f2f-927c-c8bfbcb5b00d / 9d4f53f9-83bd-8d55-6560-16bf23e21154 |
| `MovablePlatformStopSound` | FixedString | 431 | LevelTemplate | gustav, gustavdev, shared, shareddev | c9917b16-72ed-33da-0a7f-7d079a443887 / cc5b2ab0-c48a-4a1d-9336-e8f20c370a5d / 54604628-1d45-5ae0-95e9-ddb97e905137 |
| `MovementAmount` | float | 228 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 3 / 0.15 / 0.04 |
| `MovementSpeed` | float | 221 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 5 / 4 / 8 |
| `Name` | LSString | 25528 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | LOW_HouseOfHope_Cambion_Hellfire_03 / BOOK_GEN_Scroll_Parchment_Pile_C / NAT_Rock_Granite_Pillar_A_Moss |
| `NeedsImpactSFX` | bool | 72 | projectile | shared, shareddev | False / True |
| `NoiseCoverage` | float | 7 | fogVolume | gustavdev, shared | 0.9 / 0.15 / 1 |
| `NoiseFrequency` | fvec3 | 7 | fogVolume | gustavdev, shared | 0.03 0.1 0.1 / 0.15 0.15 0.15 / 0.05 0.05 0.05 |
| `NoiseRotation` | fvec3 | 7 | fogVolume | gustavdev, shared | 0 0.08726646 0 / 0.008726646 0 0 / 0 0 0 |
| `NoiseWind` | fvec3 | 7 | fogVolume | gustavdev, shared | 0 0 -1 / 0.75 0 0.5 / 0 0 0 |
| `NormalBlendingFactor` | float | 348 | decal, surface | gustav, shared, shareddev | 0.2 / 1 / 0 |
| `NotHardcore` | bool | 2 | character, item | shared | True / False |
| `ObscuredStateOverride` | uint8 | 8 | surface | shared | 2 / 1 / 3 |
| `Occlusion` | float | 1 | trigger | shared | 0 |
| `offset` | fvec2 | 344 | decal | gustav, shared, shareddev | 0 0.45 / 0 0 / 0 0.38 |
| `OffsetAMax_Bezier4` | fvec2 | 3 | projectile | shareddev | 0 8 / 0 2.5 / 0 4 |
| `OffsetAMin_Bezier4` | fvec2 | 3 | projectile | shareddev | 0 1 / 0 5 / 0 2 |
| `OffsetBMax_Bezier4` | fvec2 | 3 | projectile | shareddev | 0 8 / 0 2.5 / 0 4 |
| `OffsetBMin_Bezier4` | fvec2 | 3 | projectile | shareddev | 0 1 / 0 5 / 0 2 |
| `OffsetMax_Bezier3` | fvec2 | 14 | projectile | shared, shareddev | 0 7 / 0 12 / 0 0 |
| `OffsetMin_Bezier3` | fvec2 | 334 | projectile | gustav, gustavdev, shared, shareddev | 0 0.5 / 0 1.5 / 0 10 |
| `OnEnterDistanceOverride` | float | 7 | surface | shared | 2 / 1 |
| `OneShotTrigger` | bool | 1 | trigger | gustav | False |
| `OnlyCharacterEvents` | bool | 5 | trigger | gustav, gustavdev, shared | False |
| `OnlyOsirisEvents` | bool | 6 | trigger | gustav, shared | False |
| `OnMoveDistanceOverride` | float | 6 | surface | shared | 1.5 / 4 |
| `Opacity` | float | 290 | decal, item, scenery | gustav, gustavdev, shared, shareddev | 0.5 / 2 / 1 |
| `Optional` | bool | 1 | trigger | shared | False |
| `owner` | FixedString | 6 | item | gustavdev, shared | 21aa8a76-40ac-4d3a-881f-d6871487df6f / 6d59bb8e-90e4-4ea0-b710-280402a5bbd7 |
| `ParentGUID` | guid | 1 | trigger | shared | 00000000-0000-0000-0000-000000000000 |
| `ParentTemplateId` | FixedString | 25407 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | d8250ecf-253d-4924-9026-3dc5a5c381de / 1880a265-798a-475c-ad45-2bf6878d6dbd / ee256d56-ff13-429f-9bdd-508a1e0055f6 |
| `PathMaxArcDist` | float | 6 | projectile | shared | 18 / 8 / 0 |
| `PathMinArcDist` | float | 6 | projectile | shared | 5 / 1 / 0 |
| `PathRadius` | float | 31 | projectile | shared | 2 / 3 / 0.5 |
| `PathRepeat` | uint32 | 6 | projectile | gustav, shared | 2 |
| `PathShift` | float | 14 | projectile | shared | 0.0055 / 0.55 |
| `PermanentWarnings` | FixedString | 1 | item | shared | 82254f30-45ab-41dd-af13-8da45a866381 |
| `Persistent` | bool | 79 | LevelTemplate | gustav, shared | False |
| `PhysicsCollisionSound` | FixedString | 7 | item | gustav, shared | a2e61cd2-fc08-5baa-d73f-348251f325ad / 0c130d61-2b03-3abb-2d1d-3ea22eb35034 |
| `PhysicsFollowAnimation` | bool | 33 | item | gustavdev, shared, shareddev | False / True |
| `PhysicsOpenTemplate` | FixedString | 2782 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, surface, TileConstruction, trigger | gustav, gustavdev, shared, shareddev | b2e9924c-ff14-f826-c2f7-9acd106eac99 / ba66f4f0-936e-4346-f48b-e53a446a484f / 2a096c2c-cde9-bd99-3a17-adddfc820f87 |
| `PhysicsTemplate` | FixedString | 19524 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | 921ad48d-9ac6-7056-80b3-49dfd1b69c86 / ff6acf03-b5c4-4d58-d4ae-44c4b770e8c4 / 9ca8c9be-73e7-5c86-3674-8bd48f8bc159 |
| `PhysicsType` | int32 | 41 | trigger | gustav, gustavdev, shared, shareddev | 2 / 3 / 1 |
| `PickupSound` | FixedString | 354 | item | gustav, gustavdev, shared, shareddev | c87e342d-a717-4d86-c15a-6c0c7d9520c1 / f4a8e400-c202-1d9c-1260-00314d8e9170 / 75f7e7c8-e729-815f-ecd5-cc8d279ea5b4 |
| `Player` | uint8 | 1 | trigger | shared | 0 |
| `PortraitVisualResourceID` | FixedString | 91 | character | gustav, gustavdev, shared, shareddev | db8f68d4-c84b-2349-886a-d996f4ba5804 / 9598d919-8272-0377-d2a5-879c0012f3fd / cfd87e6a-9f86-4ca3-ecb0-c00c0ede824f |
| `PreExpose` | bool | 220 | CombinedLight, light | gustav, gustavdev, shared, shareddev | False / True |
| `PreviewPathImpactFX` | FixedString | 272 | projectile | gustav, gustavdev, shared, shareddev | VFX_UI_DestinationBeam_Projectile_01 / VFX_UI_ProjectileTrajectory_01 |
| `PreviewPathMaterial` | FixedString | 270 | projectile | gustav, gustavdev, shared, shareddev | 312a1494-a0e2-c215-cf51-bda58a6b2341 |
| `PreviewPathRadius` | float | 33 | projectile | gustavdev, shared, shareddev | 0.1 / 0.025 |
| `ProjectilePath` | uint8 | 63 | projectile | gustav, shared | 3 / 1 / 0 |
| `Race` | int8 | 147 | item | gustav, gustavdev, shared, shareddev | -1 / 2 / 0 |
| `Race` | guid | 438 | character | gustav, gustavdev, honour, shared, shareddev | 0eb594cb-8820-4be6-a58d-8be7a1a98fba / eb48ad96-0676-439d-ab44-83a2495550f8 / e9fd8f24-ce45-4180-a395-bf4c758ccd91 |
| `Radius` | float | 397 | CombinedLight, fogVolume, light, lightProbe, trigger | gustav, gustavdev, shared, shareddev | 4 / 12 / 3 |
| `RagdollTemplate` | FixedString | 8 | character | gustav, shared | f6806630-a618-9b15-2c46-8c99f7428bd8 / 43258006-b784-afc7-02a2-38b6d67fa4b3 / 96c8ec3e-f6c0-36c9-ab3a-d469af9b077c |
| `Random` | uint64 | 1 | character | shared | 9369780943625134655 |
| `ReadinessFlags` | uint32 | 3486 | character, item, scenery | gustav, gustavdev, shared, shareddev | 132 / 256 / 12 |
| `RecieveDecal` | bool | 1573 | character, CombinedLight, constellationHelper, item, light, lightProbe, prefab, projectile, scenery, surface, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | False / True |
| `RegionCameraLock` | bool | 1 | trigger | shared | True |
| `RegionCameraLockPos` | bool | 1 | trigger | shared | False |
| `RegionShroudGen` | bool | 1 | trigger | shared | True |
| `RegionShroudVisibleInWorld` | bool | 1 | trigger | shared | True |
| `RemoveDestroyedItems` | bool | 1 | surface | shared | True |
| `RenderChannel` | uint8 | 60 | item, light, scenery | gustavdev, shared, shareddev | 6 / 4 / 0 |
| `RenderMethod` | uint8 | 2 | trigger | gustav | 1 |
| `Replaces` | bool | 7 | fogVolume | gustavdev, shared | False / True |
| `RollConditions` | LSString | 24 | surface | shared, shareddev | Character() and not SavingThrow(Ability.Constitution, SourceSpellDC(11), AdvantageOnPoisoned()) / Character() and not SavingThrow(Ability.Strength,12) / Character() and not SavingThrow(Ability.Wisdom,SourceSpellDC(14)) |
| `RotateImpact` | bool | 142 | projectile | gustav, gustavdev, shared, shareddev | False / True |
| `RotateMode` | uint8 | 20 | projectile | shared, shareddev | 1 / 0 |
| `Scale` | float | 463 | character, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Spline, SplineConstruction, surface, terrain, trigger | gustav, gustavdev, shared, shareddev | 1.1 / 1.25 / 0.65 |
| `ScatteringScale` | float | 286 | CombinedLight, light | gustav, gustavdev, shared, shareddev | 0 / 15 / 1 |
| `ScrollingDirection` | fvec3 | 514 | LevelTemplate | gustav, gustavdev, shared, shareddev | 1 0 0 |
| `ScrollingDistance` | float | 514 | LevelTemplate | gustav, gustavdev, shared, shareddev | 0 / 12000 |
| `ScrollingOffset` | float | 511 | LevelTemplate | gustav, gustavdev, shared, shareddev | 0 |
| `ScrollingOrigin` | fvec3 | 503 | LevelTemplate | gustav, gustavdev, shared, shareddev | 0 0 0 / 0 -230 0 |
| `ScrollingSpeed` | float | 514 | LevelTemplate | gustav, gustavdev, shared, shareddev | 0 / 200 |
| `Seed` | uint32 | 4 | surface | shared | 666 / 10 / 0 |
| `SeeThrough` | bool | 2572 | item, scenery | gustav, gustavdev, shared, shareddev | False / True |
| `Shadow` | bool | 255 | CombinedLight, light | gustav, gustavdev, shared, shareddev | False / True |
| `ShadowPhysicsProxy` | FixedString | 161 | scenery | shared, shareddev | 08f10024-4b29-60aa-9480-0da73f95152b / b5a6a9c0-77ce-502e-2cf3-27e2ba3d8417 / 715f0ef7-6491-4972-66a3-3fd300c7b321 |
| `ShiftAMax_Bezier4` | float | 4 | projectile | shared, shareddev | 0.25 / 0 |
| `ShiftAMin_Bezier4` | float | 6 | projectile | shared, shareddev | 0.1 / 0 |
| `ShiftBMax_Bezier4` | float | 175 | projectile | gustav, gustavdev, shared, shareddev | 0.25 / 0 / 0.75 |
| `ShiftBMin_Bezier4` | float | 175 | projectile | gustav, gustavdev, shared, shareddev | 0.25 / 0 / 0.75 |
| `ShiftMax_Bezier3` | float | 12 | projectile | shared, shareddev | 0.6 / 0.8 / 0 |
| `ShiftMin_Bezier3` | float | 80 | projectile | gustav, shared, shareddev | 0.0055 / 0.55 / 0 |
| `ShootThroughType` | int8 | 430 | character, item, scenery | gustav, gustavdev, shared, shareddev | -1 / 6 / 0 |
| `ShortDescriptionParams` | LSString | 1 | item | shareddev | This container houses some of the finest fireworks money can buy. |
| `ShouldPreloadWorldTimelineActors` | bool | 1 | trigger | shared | False |
| `ShowAttachedSpellDescriptions` | bool | 38 | item | gustav, gustavdev, shared, shareddev | False / True |
| `Size` | fvec3 | 9 | fogVolume, lightProbe | gustav, gustavdev, shared | 10 10 10 / 20 20 20 / 19.1 10 17.5 |
| `SoftBodyCollisionTemplate` | FixedString | 18 | character | gustav, shared, shareddev | 22d30fb6-edd2-dec3-2cfb-4b0fae09e294 / 90072dac-2d0b-ef3a-e5a4-07339e695c6c / 4350b66a-f56a-4f2a-9c60-b5a56609afa4 |
| `SoundActivationRange` | float | 163 | LevelTemplate | gustav, gustavdev, shared, shareddev | -1 |
| `SoundAttenuation` | int16 | 1526 | character, item, scenery | gustav, gustavdev, shared, shareddev | 200 / 40 / 15 |
| `SoundEvent` | FixedString | 1 | trigger | shared | 00000000-0000-0000-0000-000000000000 |
| `SoundInitEvent` | FixedString | 1186 | character, item, scenery | gustav, gustavdev, shared, shareddev | a71c3f84-19ea-17d0-1ba6-216969b99fb3 / 3ff1d57b-6ade-2762-44df-cda5a557b6d6 / 6c516a99-a1b7-e97c-14bf-38149959b29a |
| `SoundMovementStartEvent` | FixedString | 85 | character | gustav, gustavdev, honour, shared, shareddev | b781f7a2-eb20-dd4f-6bed-c951e2481cab / c3bb321c-52e5-4909-bb93-5712fb6582ee / f0dc2a50-8689-c8c1-472e-cbb1e22587da |
| `SoundMovementStopEvent` | FixedString | 105 | character | gustav, gustavdev, honour, shared, shareddev | d7d5091b-f262-44f2-6296-0099f0baac88 / 08514b2d-9ad6-43ca-90de-868aa9e5e218 / 2a91931e-2247-7018-5afd-9b23f08b27e9 |
| `SoundObjectIndex` | uint8 | 29 | character, item | gustav, gustavdev, shared, shareddev | 3 / 255 / 4 |
| `SpawnLightRandomVerticalRangeOffset` | fvec2 | 8 | surface | shared | 0 0.1 / 0.01 0.1 / 0 0.2 |
| `SpawnLightTemplateID` | FixedString | 9 | surface | shared | 150fd237-7810-4018-9f62-37a3b9dc7a44 / 6d3e3b2c-9cf9-4296-9eb3-26b638b8b677 / 523b5022-7e1c-42a5-8c27-f8fddd04d896 |
| `SpeakerGroup` | LSString | 4 | character, item | gustav, shared | 69b61817-8458-47ac-8e78-5e855b0999ab / a84f4caa-5ad9-1572-276a-c74311e373ff |
| `Speed` | float | 333 | CombinedLight, light, projectile, Spline, trigger | gustav, gustavdev, shared, shareddev | 50 / 35 / 18 |
| `SpellSet` | FixedString | 335 | character | gustav, gustavdev, honour, shared, shareddev | RangerCompanion_ExceptionalTraining / CommonNPCActions / CommonCatSummonActions |
| `SpotSneakers` | bool | 42 | character | gustavdev, shared, shareddev | False / True |
| `StagingType` | int32 | 1 | trigger | shared | 1 |
| `StartCombatRange` | float | 4 | character, item | gustavdev, shared, shareddev | -1 / 6 / 5 |
| `StartingActive` | bool | 561 | LevelTemplate | gustav, gustavdev, shared, shareddev | False / True |
| `StartingLoaded` | bool | 515 | LevelTemplate | gustav, gustavdev, shared, shareddev | True |
| `Stats` | FixedString | 5920 | character, item | gustav, gustavdev, honour, shared, shareddev | UNI_Volo_ErsatzEye / FOR_QuasitSummon / Halfling_Melee |
| `StayInAiHints` | bool | 1 | character | shareddev | False |
| `StoryItem` | bool | 90 | item | gustav, gustavdev, shared, shareddev | False / True |
| `SubLevelName` | FixedString | 561 | LevelTemplate | gustav, gustavdev, shared, shareddev | PLT_Underdark_TeleportPlatform / BGC_Sunken_Cellar / WLD_OwlbearCave_B |
| `Summon` | FixedString | 52 | surface | shared, shareddev | 84a171b0-c44d-4689-b8fc-25e32676cd76 / bd8d5043-5cf7-427c-8dfc-829b7c6065d2 / cabefda4-6839-44e7-8e5e-7c1942fc13ca |
| `SurfaceCategory` | uint8 | 66 | surface | shared, shareddev | 3 / 12 / 11 |
| `SurfaceGrowTimer` | float | 9 | surface | shared | 0 / 0.001 / 0.05 |
| `SwarmGroup` | FixedString | 32 | character | gustav, gustavdev, shared, shareddev | PLA_Newborn_Gnolls / LOW_Sewers_MagmaMephitBabies / BloodSkeletonSwarm |
| `Team` | uint8 | 1 | trigger | shared | 0 |
| `TechnicalDescriptionParams` | LSString | 39 | item | gustav, shared, shareddev | DealDamage(1d6,Fire) / Distance(9); DealDamage(4d6,Fire) / Distance(12) |
| `TemplateAfterDestruction` | FixedString | 519 | LevelTemplate | gustav, gustavdev, shared | 05c37d6c-71e7-432d-a8f0-e59727833482 / 18ab9546-bfd0-4dfb-a6cf-2ebeb1d31efc / 1873d47b-807d-42e9-a5fd-d08444dd0d03 |
| `TextureMapping` | uint8 | 16 | light | gustav, shared, shareddev | 0 |
| `Tiling` | fvec2 | 341 | decal | gustav, shared, shareddev | 0.45 1 / 0.27 0.27 / 0.15 0.15 |
| `Tooltip` | uint8 | 816 | item | gustav, gustavdev, shared, shareddev | 2 / 1 / 0 |
| `TrailFX` | FixedString | 228 | projectile | gustav, gustavdev, shared, shareddev | VFX_Projectiles_Damage_Fire_ChromaticOrb_Projectile_01 / VFX_Enemies_Spider_ToxicSpit_Projectile_01 / VFX_Projectiles_Damage_Fire_FireBolt_Projectile_01 |
| `TrajectoryType` | uint8 | 132 | projectile | gustav, gustavdev, shared, shareddev | 2 / 1 / 0 |
| `TransitionDistance` | float | 9 | fogVolume, lightProbe | gustav, gustavdev, shared | 2 / 0.4 / 1 |
| `TreasureLevel` | int32 | 1 | item | shared | -1 |
| `TreasureOnDestroy` | bool | 641 | item | gustav, gustavdev, shared, shareddev | False / True |
| `TriggerCameraLockPos` | bool | 1 | trigger | shared | False |
| `TriggerCrimeArea` | int16 | 2 | trigger | shared | 0 |
| `TriggerGameCameraBehavior` | int32 | 1 | trigger | shared | 0 |
| `TriggerType` | FixedString | 39 | trigger | gustav, shared, shareddev | TriggerSoundVolume / TriggerAtmosphere / RoomTrigger |
| `Type` | FixedString | 25528 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | projectile / LevelTemplate / scenery |
| `UnequipSound` | FixedString | 50 | item | gustav, gustavdev, shared, shareddev | f69d46c0-213b-038a-5281-9533b61dca7b / 7be8fdbc-81c2-4258-7826-5bc26f262f5b / f4c24367-83af-484e-bcc5-0438b8e64dec |
| `Unimportant` | bool | 24 | item | gustav, shared, shareddev | False / True |
| `UseOcclusion` | bool | 30 | character, item, trigger | gustav, gustavdev, shared, shareddev | False / True |
| `UseOnDistance` | bool | 5 | item | gustavdev, shared | False / True |
| `UsePartyLevelForTreasureLevel` | bool | 8 | item | shared, shareddev | False |
| `UseRemotely` | bool | 4 | item | gustavdev, shareddev | True |
| `UseSound` | FixedString | 239 | item | gustav, gustavdev, shared, shareddev | 2960f025-834b-52cb-c58f-d921d985564d / a41724e5-f266-d2bc-f5b7-640a1e9d02db / 817b988e-3cc1-78e6-54bc-45da77580f54 |
| `UseSoundClustering` | bool | 22 | character | gustav, gustavdev, shared, shareddev | False |
| `UseSoundOcclusion` | bool | 255 | LevelTemplate | gustav, gustavdev, shared, shareddev | True |
| `UseTemperature` | bool | 266 | CombinedLight, light | gustav, gustavdev, shared, shareddev | False / True |
| `UsingGizmoColorOverride` | bool | 24 | trigger | gustav, shared, shareddev | False |
| `VelocityMode` | uint8 | 244 | projectile | gustav, gustavdev, shared, shareddev | 2 / 1 / 0 |
| `VFXScale` | float | 9 | character | gustav, gustavdev, honour, shared, shareddev | 1.1 / 1.05 / 1.15 |
| `VisualSetResourceID` | FixedString | 2 | character | shared | e22446a6-9b83-4465-b444-3c6ac4c9c772 / 00000000-0000-0000-0000-000000000000 |
| `VisualTemplate` | FixedString | 20642 | character, CombinedLight, constellation, constellationHelper, decal, fogVolume, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, Schematic, Spline, SplineConstruction, surface, terrain, TileConstruction, trigger | gustav, gustavdev, honour, shared, shareddev | 3a8784e6-b650-2cea-1ea3-d051ec3ab15d / 8b261162-e116-d2e2-73d9-e5109f8f3b93 / f0ae2d02-f979-3340-7f5f-9d096ecfaae0 |
| `VocalAlertResourceID` | FixedString | 176 | character | gustav, gustavdev, shared, shareddev | 2ebebd33-596f-edea-a781-24177c129887 / 8a5b1ba6-2d03-2df8-1768-59b5bc4845c4 / 1c46a3fc-070d-4f2b-b555-622d2f107a06 |
| `VocalAngryResourceID` | FixedString | 185 | character | gustav, gustavdev, shared, shareddev | 7ad6c6ed-f48f-4337-140d-eb274efaa5e7 / 95eb4ea2-a766-db0d-cb1d-0ed5a4e1bf3b / 650bf105-11ee-fde9-f41d-5dcfda83871d |
| `VocalAnticipationResourceID` | FixedString | 86 | character | gustav, gustavdev, shared, shareddev | f978a189-ed06-fdf5-6ec3-4df585c42997 / 5569078b-169e-358f-94d3-2583839392f3 / e804394e-0e39-497a-afa3-5bb52e4a9cba |
| `VocalAttackResourceID` | FixedString | 268 | character | gustav, gustavdev, honour, shared, shareddev | decf8c50-d783-c1a7-a92e-029932e69c12 / 12b2f214-62db-a079-3a3c-b9d5023a0433 / 40ea1faa-fa18-438c-a7de-e6502fb2e432 |
| `VocalAwakeResourceID` | FixedString | 207 | character | gustav, gustavdev, honour, shared, shareddev | b0456735-95f9-3cd2-f76f-9ad1d3676589 / e52a7726-7a6d-d041-0198-f91b098d8d7b / a1db6bf7-4e40-4cc2-ba3e-dcd106ea3b4e |
| `VocalBoredResourceID` | FixedString | 188 | character | gustav, gustavdev, shared, shareddev | f162374d-ec77-da0b-7561-b4c1921c4d60 / 6e6aca73-3d17-33ec-7a12-0ee713dd839f / 93080f52-6904-df3f-fc08-ef56ea2ce95e |
| `VocalBuffResourceID` | FixedString | 78 | character | gustav, gustavdev, honour, shared, shareddev | 6ad7080a-2533-4159-bd3b-0c301d938a9b / a1db6bf7-4e40-4cc2-ba3e-dcd106ea3b4e / f344d31a-995f-eba2-00b6-80e3ecd8f994 |
| `VocalDeathResourceID` | FixedString | 286 | character | gustav, gustavdev, honour, shared, shareddev | b586f789-d290-f56a-f7c2-3a8a39f71b53 / 0cd61230-6240-7606-abaf-dd5c367e1390 / 0c5b7b14-089b-bbde-55f0-ebafb65f6161 |
| `VocalDodgeResourceID` | FixedString | 265 | character | gustav, gustavdev, honour, shared, shareddev | bc3bebcc-8fbe-79f1-9304-62c6e1f78dc2 / 76625ed6-3179-f59d-d0b8-c9658f7c1e24 / 6f2fd945-10df-4009-badc-bb065ed95fc8 |
| `VocalEffortsResourceID` | FixedString | 141 | character | gustav, gustavdev, honour, shared, shareddev | a57e063f-f974-8d35-1fab-f8f9d75dcfa4 / 6bdbc39c-0414-c3a2-e065-c2882eab361a / 95b6b7f3-f06c-7b9d-1d93-39f58d0a89a9 |
| `VocalExhaustedResourceID` | FixedString | 175 | character | gustav, gustavdev, shared, shareddev | 55da6c6d-2cb8-ec4b-b9ce-c3fa9a231790 / 4d5eb40c-b546-451f-9e17-4bc6a1eac786 / 092058b7-5c2a-4ced-9f44-7d908c559094 |
| `VocalFallResourceID` | FixedString | 138 | character | gustav, gustavdev, honour, shared, shareddev | d22569e3-ef14-b831-7194-5467412b3f8e / bbc7443f-38ee-373d-a3b2-a9b262dffe26 / 7a9e9ddd-313c-31e1-1c3a-f8e6594f2361 |
| `VocalGaspResourceID` | FixedString | 30 | character | gustav, gustavdev, honour, shared, shareddev | 63eb6781-6826-370f-aa83-9487a0d51544 / 7706009c-83df-1e6e-3ead-65bf77d983ba / 1896ec0d-e17b-bc47-b994-d77cad0f66b9 |
| `VocalIdle1ResourceID` | FixedString | 110 | character | gustav, gustavdev, honour, shared, shareddev | e11664a4-2126-ff10-60f8-b5e94a342527 / 84cc328b-03e8-45f2-a30c-8b892ff6e1c0 / fc424747-71f7-4828-84d5-95a1d2eae8ae |
| `VocalIdle2ResourceID` | FixedString | 61 | character | gustav, gustavdev, shared, shareddev | e11664a4-2126-ff10-60f8-b5e94a342527 / f240303e-820c-27f3-cc33-f34c9b1e0292 / 30c50c6f-f98b-8369-d429-b6b678042107 |
| `VocalIdle3ResourceID` | FixedString | 46 | character | gustav, gustavdev, shared, shareddev | 7d4eb665-2786-4bb3-ad65-b85549563c1e / 0ea8e279-2db6-a9e3-c23f-8ae72e180b63 / 586f0e98-13e5-e173-2923-0ef3a588eedf |
| `VocalIdleCombat1ResourceID` | FixedString | 64 | character | gustavdev, shared, shareddev | 283d6d88-ad11-4187-b007-3a95c1ea915d / 98b4624e-cda1-4c6d-bfd5-71721ebb4e9d / 13a2a97e-e478-3f20-ece1-d4f2a48b8059 |
| `VocalIdleCombat2ResourceID` | FixedString | 44 | character | gustavdev, shared, shareddev | 3cea775f-658e-48a2-40f9-b137c41d077c / 16412081-b9de-4c00-aaed-44b4c641b6e4 / 672bfae2-ad74-2c4f-8e64-4aa3d13305bf |
| `VocalIdleCombat3ResourceID` | FixedString | 30 | character | gustavdev, shared, shareddev | 562f5e8e-b450-4f74-99e4-1fd7d2f6cdb9 / b1388339-d63d-81ee-d609-13432bb16ce5 / 4f0cfcb1-319d-4751-b865-98a5a884a9f4 |
| `VocalInitiativeResourceID` | FixedString | 172 | character | gustav, gustavdev, honour, shared, shareddev | 2bdb111e-a67a-93f2-ec83-2d78225e57c8 / f5d397ca-1ab6-a4a7-a802-9a9305da6ab5 / d62ecdd7-1245-ffc9-3db8-b9c188d4f756 |
| `VocalLaughterManiacalResourceID` | FixedString | 56 | character | gustav, gustavdev, honour, shared, shareddev | df225c8c-e5fd-4788-b47c-c33b97ccdc3a / 0f236535-11f2-425c-ae39-2c6634c35d41 / 19675971-6ffa-4c34-ae4a-3dcf2a13a665 |
| `VocalLaughterResourceID` | FixedString | 80 | character | gustav, gustavdev, honour, shared, shareddev | 86615338-3c11-47ef-b9f0-94efa7e329fc / ab41ef63-348e-7399-6e63-b4143769ad08 / 71d81811-9692-4d28-8d7c-87fe56e870eb |
| `VocalNoneResourceID` | FixedString | 25 | character | gustav, gustavdev, honour, shared | 2af5ab18-2087-45c6-94a8-a968190d618a |
| `VocalPainResourceID` | FixedString | 283 | character | gustav, gustavdev, honour, shared, shareddev | 361659d5-6297-46d4-b36c-7fe6131bdf30 / 8d8904da-e80e-e40b-c9ae-160f61a69d1e / 2fdbf6c6-72c6-43a4-8001-0d4b5a74ed52 |
| `VocalRebornResourceID` | FixedString | 46 | character | gustav, gustavdev, shared, shareddev | 179a3721-b9ca-48d5-81bb-e80128fcb409 / 21edcffc-6a14-76fe-5393-4f9f09338f30 / dd98f8a0-4d25-b67b-7215-394739cfa640 |
| `VocalRecoverResourceID` | FixedString | 110 | character | gustav, gustavdev, honour, shared, shareddev | bfc0e3fa-1e2d-136a-7cb7-ba26819fe257 / ca2cc673-948a-e098-90b1-f2204d573aae / 6bbd38ed-8e59-0c4a-be7d-42c87bb7d367 |
| `VocalRelaxedResourceID` | FixedString | 185 | character | gustav, gustavdev, shared, shareddev | a57e063f-f974-8d35-1fab-f8f9d75dcfa4 / f7d73a55-e753-ccb5-05c5-6bf71b8f2653 / f588feeb-362d-4ad1-9d4f-88eb94101a1d |
| `VocalShoutResourceID` | FixedString | 131 | character | gustav, gustavdev, honour, shared, shareddev | 3c8e0eef-8482-4ccf-91f1-3100303d1d80 / 91b41a57-6a68-5c0d-b3d4-b8a47c7c5138 / dc343e4c-450c-364c-0990-72768d5b6ba6 |
| `VocalSnoreResourceID` | FixedString | 186 | character | gustav, gustavdev, honour, shared, shareddev | 92abbdcc-d33c-8b59-2f0e-09e145d2fae0 / 2aa7ee3e-3f8e-ef10-a8b2-a1956495e44a / 1c3322b0-d250-df48-63a1-c12931b579ca |
| `VocalSpawnResourceID` | FixedString | 139 | character | gustav, gustavdev, shared, shareddev | 05a18217-7cb8-44ec-8611-f038c505aad7 / 29a2bd81-634a-7972-adf6-3cf381bbd063 / d4a6c307-954a-414f-a00c-f90b5355fc85 |
| `VocalVictoryResourceID` | FixedString | 176 | character | gustav, gustavdev, honour, shared, shareddev | a32486b8-3ac0-7047-63e1-2c1dd7f1d48f / 51994cfd-7015-7f9d-7222-2a291218b594 / 05a18217-7cb8-44ec-8611-f038c505aad7 |
| `VocalWeakResourceID` | FixedString | 233 | character | gustav, gustavdev, honour, shared, shareddev | f7cb5e5b-9261-df56-555f-c7b1f13ec0e8 / 911c03bf-de92-ec99-d4c3-b174ee7ac922 / 377cbb98-e1e4-5521-e0ca-c9bc87c4c922 |
| `VolumetricLightCollisionProbability` | float | 16 | light | gustav, shared, shareddev | 0.0001 |
| `VolumetricLightIntensity` | float | 16 | light | gustav, shared, shareddev | 0.0001 / 0.05 / 5000 |
| `VolumetricShadow` | bool | 203 | CombinedLight, light | gustav, gustavdev, shared, shareddev | False / True |
| `Wadable` | bool | 1385 | item, scenery | gustav, gustavdev, shared, shareddev | False / True |
| `WadableSurfaceType` | FixedString | 208 | item, scenery | gustav, gustavdev, shared, shareddev | SurfaceDeepWater |
| `WalkOn` | bool | 3783 | item, scenery | gustav, gustavdev, shared, shareddev | False / True |
| `WalkThrough` | bool | 3501 | character, item, scenery | gustav, gustavdev, shared, shareddev | False / True |
| `Zoom` | bool | 1 | trigger | shared | True |

## TYPE: scenery (10249 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `ParentTemplateId` | 10249 | 100% |
| `_OriginalFileVersion_` | 10249 | 100% |
| `MapKey` | 10249 | 100% |
| `Type` | 10249 | 100% |
| `LevelName` | 10249 | 100% |
| `Name` | 10249 | 100% |
| `VisualTemplate` | 10142 | 99% |
| `PhysicsTemplate` | 9813 | 95.7% |
| `CoverAmount` | 3449 | 33.7% |
| `WalkOn` | 2535 | 24.7% |
| `SeeThrough` | 2350 | 22.9% |
| `WalkThrough` | 1767 | 17.2% |
| `CanClimbOn` | 1688 | 16.5% |
| `CanShootThrough` | 1680 | 16.4% |
| `DisplayName` | 1318 | 12.9% |
| `CanClickThrough` | 1274 | 12.4% |
| `ReadinessFlags` | 913 | 8.9% |
| `RecieveDecal` | 796 | 7.8% |
| `CastShadow` | 656 | 6.4% |
| `Fadeable` | 597 | 5.8% |
| `HiddenFromMinimapRendering` | 556 | 5.4% |
| `SoundAttenuation` | 438 | 4.3% |
| `Wadable` | 382 | 3.7% |
| `CanShineThrough` | 349 | 3.4% |
| `IsPointerBlocker` | 340 | 3.3% |
| `HierarchyOnlyFade` | 339 | 3.3% |
| `IsBlocker` | 331 | 3.2% |
| `Flag` | 317 | 3.1% |
| `PhysicsOpenTemplate` | 298 | 2.9% |
| `HasGameplayValue` | 265 | 2.6% |
| `CameraOffset` | 254 | 2.5% |
| `GroupID` | 254 | 2.5% |
| `LoopSound` | 194 | 1.9% |
| `ShootThroughType` | 188 | 1.8% |
| `ShadowPhysicsProxy` | 161 | 1.6% |
| `FadeIn` | 143 | 1.4% |
| `IsDecorative` | 137 | 1.3% |
| `Scale` | 112 | 1.1% |
| `WadableSurfaceType` | 67 | 0.7% |
| `AllowCameraMovement` | 64 | 0.6% |
| `RenderChannel` | 49 | 0.5% |
| `SoundInitEvent` | 40 | 0.4% |
| `CollideWithCamera` | 24 | 0.2% |
| `IsForcedType` | 19 | 0.2% |
| `IsShadowProxy` | 14 | 0.1% |
| `Icon` | 8 | 0.1% |
| `FadeGroup` | 8 | 0.1% |
| `Opacity` | 6 | 0.1% |
| `GenerateRunningDeepWater` | 4 | 0% |

## TYPE: item (9325 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `_OriginalFileVersion_` | 9325 | 100% |
| `Name` | 9325 | 100% |
| `ParentTemplateId` | 9325 | 100% |
| `Type` | 9325 | 100% |
| `LevelName` | 9325 | 100% |
| `MapKey` | 9325 | 100% |
| `DisplayName` | 7558 | 81.1% |
| `VisualTemplate` | 7352 | 78.8% |
| `PhysicsTemplate` | 6621 | 71% |
| `Icon` | 5572 | 59.8% |
| `Stats` | 4664 | 50% |
| `Description` | 3436 | 36.8% |
| `ReadinessFlags` | 2469 | 26.5% |
| `CanShootThrough` | 1902 | 20.4% |
| `WalkThrough` | 1729 | 18.5% |
| `CoverAmount` | 1535 | 16.5% |
| `WalkOn` | 1248 | 13.4% |
| `CanClimbOn` | 1134 | 12.2% |
| `LoopSound` | 1132 | 12.1% |
| `SoundInitEvent` | 1087 | 11.7% |
| `CanClickThrough` | 1085 | 11.6% |
| `SoundAttenuation` | 1084 | 11.6% |
| `Flag` | 1051 | 11.3% |
| `IsPointerBlocker` | 1016 | 10.9% |
| `Wadable` | 1003 | 10.8% |
| `Tooltip` | 816 | 8.8% |
| `IsInspector` | 722 | 7.7% |
| `TreasureOnDestroy` | 641 | 6.9% |
| `GravityType` | 575 | 6.2% |
| `RecieveDecal` | 523 | 5.6% |
| `Faction` | 522 | 5.6% |
| `maxStackAmount` | 521 | 5.6% |
| `LevelOverride` | 493 | 5.3% |
| `InventoryType` | 434 | 4.7% |
| `DropSound` | 367 | 3.9% |
| `PickupSound` | 354 | 3.8% |
| `InventoryMoveSound` | 349 | 3.7% |
| `CanBeMoved` | 330 | 3.5% |
| `TechnicalDescription` | 317 | 3.4% |
| `ImpactSound` | 315 | 3.4% |
| `EquipmentTypeID` | 301 | 3.2% |
| `PhysicsOpenTemplate` | 265 | 2.8% |
| `CanBePickedUp` | 264 | 2.8% |
| `OnUseDescription` | 250 | 2.7% |
| `ShootThroughType` | 241 | 2.6% |
| `UseSound` | 239 | 2.6% |
| `Archetype` | 225 | 2.4% |
| `GroupID` | 224 | 2.4% |
| `BloodSurfaceType` | 222 | 2.4% |
| `SeeThrough` | 222 | 2.4% |
| `AiHint` | 217 | 2.3% |
| `AttackableWhenClickThrough` | 216 | 2.3% |
| `CameraOffset` | 214 | 2.3% |
| `IsPortal` | 214 | 2.3% |
| `ExamineRotation` | 211 | 2.3% |
| `HasGameplayValue` | 211 | 2.3% |
| `MeshProxy` | 184 | 2% |
| `Fadeable` | 175 | 1.9% |
| `HierarchyOnlyFade` | 168 | 1.8% |
| `CanBeImprovisedWeapon` | 164 | 1.8% |
| `IsPublicDomain` | 160 | 1.7% |
| `CanJoinCombat` | 152 | 1.6% |
| `Race` | 147 | 1.6% |
| `WadableSurfaceType` | 141 | 1.5% |
| `BookType` | 136 | 1.5% |
| `Scale` | 122 | 1.3% |
| `Opacity` | 118 | 1.3% |
| `DestroyWithStack` | 110 | 1.2% |
| `Destroyed` | 106 | 1.1% |
| `ConstellationConfigName` | 98 | 1.1% |
| `StoryItem` | 90 | 1% |
| `CastShadow` | 84 | 0.9% |
| `DisplayNameAlchemy` | 83 | 0.9% |
| `UnknownDescription` | 78 | 0.8% |
| `InteractionFilterType` | 68 | 0.7% |
| `EquipSound` | 65 | 0.7% |
| `TechnicalDescriptionParams` | 63 | 0.7% |
| `IsInteractionDisabled` | 56 | 0.6% |
| `Hostile` | 52 | 0.6% |
| `IsBlueprintDisabledByDefault` | 50 | 0.5% |
| `UnequipSound` | 50 | 0.5% |
| `AnubisConfigName` | 49 | 0.5% |
| `FreezeGravity` | 49 | 0.5% |
| `ColorPreset` | 44 | 0.5% |
| `FadeIn` | 42 | 0.5% |
| `DevComment` | 41 | 0.4% |
| `IsTrap` | 40 | 0.4% |
| `CanFight` | 38 | 0.4% |
| `ShowAttachedSpellDescriptions` | 38 | 0.4% |
| `PhysicsFollowAnimation` | 33 | 0.4% |
| `DisarmDifficultyClassID` | 33 | 0.4% |
| `UnknownDisplayName` | 31 | 0.3% |
| `Key` | 31 | 0.3% |
| `HiddenFromMinimapRendering` | 29 | 0.3% |
| `DefaultState` | 29 | 0.3% |
| `CanBePickpocketed` | 28 | 0.3% |
| `IsKey` | 26 | 0.3% |
| `Unimportant` | 24 | 0.3% |
| `UseOcclusion` | 20 | 0.2% |
| `CanShineThrough` | 20 | 0.2% |
| `AllowSummonGenericUse` | 19 | 0.2% |
| `IgnoreGenerics` | 17 | 0.2% |
| `IsSurfaceCloudBlocker` | 16 | 0.2% |
| `IsSurfaceBlocker` | 15 | 0.2% |
| `CinematicArenaFlags` | 11 | 0.1% |
| `Amount` | 10 | 0.1% |
| `RenderChannel` | 9 | 0.1% |
| `TemplateName` | 9 | 0.1% |
| `UsePartyLevelForTreasureLevel` | 8 | 0.1% |
| `IsPlatformOwner` | 8 | 0.1% |
| `ActivationGroupId` | 7 | 0.1% |
| `PhysicsCollisionSound` | 7 | 0.1% |
| `owner` | 6 | 0.1% |
| `HardcoreOnly` | 6 | 0.1% |
| `ForceAffectedByAura` | 5 | 0.1% |
| `DisarmDC` | 5 | 0.1% |
| `IsBoss` | 5 | 0.1% |
| `UseOnDistance` | 5 | 0.1% |
| `ContainerAutoAddOnPickup` | 5 | 0.1% |
| `ShortDescription` | 5 | 0.1% |
| `IsPortalProhibitedToPlayers` | 4 | 0% |
| `AllowSummonTeleport` | 4 | 0% |
| `UseRemotely` | 4 | 0% |
| `IsDroppedOnDeath` | 4 | 0% |
| `ContainerContentFilterCondition` | 4 | 0% |
| `BlockAoEDamage` | 4 | 0% |
| `IsDecorative` | 3 | 0% |
| `IsBlocker` | 3 | 0% |
| `CombatName` | 2 | 0% |
| `IsSourceContainer` | 2 | 0% |
| `BloodType` | 2 | 0% |
| `SpeakerGroup` | 2 | 0% |
| `MapMarkerStyle` | 2 | 0% |
| `FadeGroup` | 1 | 0% |
| `IsImprovisedWeapon` | 1 | 0% |
| `NotHardcore` | 1 | 0% |
| `IsShadowProxy` | 1 | 0% |
| `LockDifficultyClassID` | 1 | 0% |
| `ShortDescriptionParams` | 1 | 0% |
| `SoundObjectIndex` | 1 | 0% |
| `MaterialPreset` | 1 | 0% |
| `IsHuge` | 1 | 0% |
| `InteractionFilterRequirement` | 1 | 0% |
| `TreasureLevel` | 1 | 0% |
| `AiUseCombatHelper` | 1 | 0% |
| `PermanentWarnings` | 1 | 0% |
| `LightChannel` | 1 | 0% |
| `StartCombatRange` | 1 | 0% |
| `Floating` | 1 | 0% |
| `LockDC` | 1 | 0% |

## TYPE: character (2454 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `ParentTemplateId` | 2454 | 100% |
| `MapKey` | 2454 | 100% |
| `Type` | 2454 | 100% |
| `_OriginalFileVersion_` | 2454 | 100% |
| `Name` | 2454 | 100% |
| `LevelName` | 2454 | 100% |
| `Icon` | 1831 | 74.6% |
| `CharacterVisualResourceID` | 1757 | 71.6% |
| `Stats` | 1256 | 51.2% |
| `DisplayName` | 1028 | 41.9% |
| `Archetype` | 723 | 29.5% |
| `GeneratePortrait` | 684 | 27.9% |
| `AnubisConfigName` | 561 | 22.9% |
| `Flag` | 463 | 18.9% |
| `LevelOverride` | 454 | 18.5% |
| `Equipment` | 444 | 18.1% |
| `Race` | 438 | 17.8% |
| `VisualTemplate` | 368 | 15% |
| `AiHint` | 345 | 14.1% |
| `SpellSet` | 335 | 13.7% |
| `PhysicsTemplate` | 320 | 13% |
| `Faction` | 292 | 11.9% |
| `VocalDeathResourceID` | 286 | 11.7% |
| `VocalPainResourceID` | 283 | 11.5% |
| `VocalAttackResourceID` | 268 | 10.9% |
| `VocalDodgeResourceID` | 265 | 10.8% |
| `VocalWeakResourceID` | 233 | 9.5% |
| `EquipmentRace` | 214 | 8.7% |
| `BloodSurfaceType` | 208 | 8.5% |
| `VocalAwakeResourceID` | 207 | 8.4% |
| `VocalBoredResourceID` | 188 | 7.7% |
| `VocalSnoreResourceID` | 186 | 7.6% |
| `VocalAngryResourceID` | 185 | 7.5% |
| `VocalRelaxedResourceID` | 185 | 7.5% |
| `VocalAlertResourceID` | 176 | 7.2% |
| `VocalVictoryResourceID` | 176 | 7.2% |
| `VocalExhaustedResourceID` | 175 | 7.1% |
| `VocalInitiativeResourceID` | 172 | 7% |
| `BloodType` | 152 | 6.2% |
| `AnimationSetResourceID` | 146 | 5.9% |
| `IsLootable` | 145 | 5.9% |
| `LightID` | 144 | 5.9% |
| `LadderLoopSpeed` | 143 | 5.8% |
| `DeathEffect` | 141 | 5.7% |
| `VocalEffortsResourceID` | 141 | 5.7% |
| `VocalSpawnResourceID` | 139 | 5.7% |
| `VocalFallResourceID` | 138 | 5.6% |
| `VocalShoutResourceID` | 131 | 5.3% |
| `IsEquipmentLootable` | 112 | 4.6% |
| `VocalIdle1ResourceID` | 110 | 4.5% |
| `VocalRecoverResourceID` | 110 | 4.5% |
| `ExplodedResourceID` | 106 | 4.3% |
| `SoundMovementStopEvent` | 105 | 4.3% |
| `ReadinessFlags` | 104 | 4.2% |
| `PortraitVisualResourceID` | 91 | 3.7% |
| `DisintegratedResourceID` | 91 | 3.7% |
| `VocalAnticipationResourceID` | 86 | 3.5% |
| `SoundMovementStartEvent` | 85 | 3.5% |
| `CanClimbLadders` | 85 | 3.5% |
| `CanBePickedUp` | 84 | 3.4% |
| `VocalLaughterResourceID` | 80 | 3.3% |
| `VocalBuffResourceID` | 78 | 3.2% |
| `LightChannel` | 77 | 3.1% |
| `CanFight` | 72 | 2.9% |
| `LadderAttachOffset` | 70 | 2.9% |
| `VocalIdleCombat1ResourceID` | 64 | 2.6% |
| `DeathRaycastMaxLength` | 63 | 2.6% |
| `VocalIdle2ResourceID` | 61 | 2.5% |
| `SoundInitEvent` | 59 | 2.4% |
| `Scale` | 58 | 2.4% |
| `RecieveDecal` | 56 | 2.3% |
| `VocalLaughterManiacalResourceID` | 56 | 2.3% |
| `Title` | 56 | 2.3% |
| `ActiveCharacterLightID` | 54 | 2.2% |
| `GroupID` | 52 | 2.1% |
| `InventoryType` | 50 | 2% |
| `CanBeTeleported` | 47 | 1.9% |
| `VocalIdle3ResourceID` | 46 | 1.9% |
| `VocalRebornResourceID` | 46 | 1.9% |
| `VocalIdleCombat2ResourceID` | 44 | 1.8% |
| `FoleyMediumResourceID` | 43 | 1.8% |
| `PhysicsOpenTemplate` | 42 | 1.7% |
| `CameraOffset` | 42 | 1.7% |
| `SpotSneakers` | 42 | 1.7% |
| `ForceLifetimeDeath` | 41 | 1.7% |
| `HasGameplayValue` | 41 | 1.7% |
| `CanOpenDoors` | 39 | 1.6% |
| `CriticalHitType` | 33 | 1.3% |
| `FoleyLongResourceID` | 33 | 1.3% |
| `SwarmGroup` | 32 | 1.3% |
| `IsInspector` | 31 | 1.3% |
| `VocalIdleCombat3ResourceID` | 30 | 1.2% |
| `VocalGaspResourceID` | 30 | 1.2% |
| `IsPlayer` | 28 | 1.1% |
| `SoundObjectIndex` | 28 | 1.1% |
| `DisableEquipping` | 27 | 1.1% |
| `DeathRaycastMinLength` | 26 | 1.1% |
| `CombatGroupID` | 26 | 1.1% |
| `VocalNoneResourceID` | 26 | 1.1% |
| `DevComment` | 26 | 1.1% |
| `FoleyShortResourceID` | 22 | 0.9% |
| `IsSimpleCharacter` | 22 | 0.9% |
| `UseSoundClustering` | 22 | 0.9% |
| `SoftBodyCollisionTemplate` | 19 | 0.8% |
| `CanJoinCombat` | 18 | 0.7% |
| `IsBoss` | 14 | 0.6% |
| `CanShootThrough` | 13 | 0.5% |
| `UseOcclusion` | 9 | 0.4% |
| `VFXScale` | 9 | 0.4% |
| `RagdollTemplate` | 8 | 0.3% |
| `CanConsumeItems` | 6 | 0.2% |
| `WalkThrough` | 5 | 0.2% |
| `LadderDetachSpeed` | 5 | 0.2% |
| `LadderAttachSpeed` | 5 | 0.2% |
| `AliveInventoryType` | 4 | 0.2% |
| `ExplosionFX` | 4 | 0.2% |
| `DefaultState` | 4 | 0.2% |
| `SoundAttenuation` | 4 | 0.2% |
| `CombatName` | 3 | 0.1% |
| `AvoidTraps` | 3 | 0.1% |
| `StartCombatRange` | 3 | 0.1% |
| `CastShadow` | 2 | 0.1% |
| `SpeakerGroup` | 2 | 0.1% |
| `JumpUpLadders` | 2 | 0.1% |
| `TemplateName` | 2 | 0.1% |
| `VisualSetResourceID` | 2 | 0.1% |
| `ShootThroughType` | 1 | 0% |
| `ActivationGroupId` | 1 | 0% |
| `CanWalkThroughDoors` | 1 | 0% |
| `Random` | 1 | 0% |
| `DefaultDialog` | 1 | 0% |
| `NotHardcore` | 1 | 0% |
| `InfluenceTreasureLevel` | 1 | 0% |
| `IsTradable` | 1 | 0% |
| `DeathRaycastVerticalLength` | 1 | 0% |
| `StayInAiHints` | 1 | 0% |

## TYPE: prefab (820 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `MapKey` | 820 | 100% |
| `Name` | 820 | 100% |
| `_OriginalFileVersion_` | 820 | 100% |
| `LevelName` | 820 | 100% |
| `Type` | 820 | 100% |
| `PhysicsTemplate` | 819 | 99.9% |
| `GroupID` | 819 | 99.9% |
| `VisualTemplate` | 819 | 99.9% |
| `Flag` | 819 | 99.9% |
| `CameraOffset` | 807 | 98.4% |
| `HasGameplayValue` | 804 | 98% |
| `ParentTemplateId` | 717 | 87.4% |
| `PhysicsOpenTemplate` | 559 | 68.2% |
| `Scale` | 107 | 13% |
| `DevComment` | 2 | 0.2% |
| `CastShadow` | 1 | 0.1% |
| `RecieveDecal` | 1 | 0.1% |

## TYPE: TileConstruction (579 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `LevelName` | 579 | 100% |
| `MapKey` | 579 | 100% |
| `Name` | 579 | 100% |
| `ParentTemplateId` | 579 | 100% |
| `Type` | 579 | 100% |
| `_OriginalFileVersion_` | 579 | 100% |
| `VisualTemplate` | 431 | 74.4% |
| `CameraOffset` | 421 | 72.7% |
| `GroupID` | 421 | 72.7% |
| `Flag` | 421 | 72.7% |
| `PhysicsTemplate` | 421 | 72.7% |
| `HasGameplayValue` | 419 | 72.4% |
| `PhysicsOpenTemplate` | 373 | 64.4% |
| `HiddenFromMinimapRendering` | 10 | 1.7% |
| `RecieveDecal` | 4 | 0.7% |

## TYPE: LevelTemplate (561 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `CameraOffset` | 561 | 100% |
| `_OriginalFileVersion_` | 561 | 100% |
| `Type` | 561 | 100% |
| `StartingActive` | 561 | 100% |
| `PhysicsTemplate` | 561 | 100% |
| `GroupID` | 561 | 100% |
| `MapKey` | 561 | 100% |
| `Name` | 561 | 100% |
| `Flag` | 561 | 100% |
| `SubLevelName` | 561 | 100% |
| `VisualTemplate` | 561 | 100% |
| `LevelName` | 561 | 100% |
| `ParentTemplateId` | 559 | 99.6% |
| `HasGameplayValue` | 555 | 98.9% |
| `TemplateAfterDestruction` | 532 | 94.8% |
| `StartingLoaded` | 515 | 91.8% |
| `ScrollingDistance` | 514 | 91.6% |
| `ScrollingDirection` | 514 | 91.6% |
| `ScrollingSpeed` | 514 | 91.6% |
| `IsScrollingObject` | 514 | 91.6% |
| `ScrollingOffset` | 511 | 91.1% |
| `IsMoving` | 505 | 90% |
| `ScrollingOrigin` | 503 | 89.7% |
| `PhysicsOpenTemplate` | 485 | 86.5% |
| `LevelTemplateType` | 482 | 85.9% |
| `IsDynamicLayer` | 471 | 84% |
| `MovablePlatformStartSound` | 431 | 76.8% |
| `MovablePlatformStopSound` | 431 | 76.8% |
| `UseSoundOcclusion` | 255 | 45.5% |
| `SoundActivationRange` | 163 | 29.1% |
| `IsCinematic` | 80 | 14.3% |
| `Persistent` | 79 | 14.1% |
| `Scale` | 10 | 1.8% |
| `ConstellationConfigName` | 1 | 0.2% |
| `HiddenFromMinimapRendering` | 1 | 0.2% |
| `IsShadowProxy` | 1 | 0.2% |

## TYPE: projectile (480 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `_OriginalFileVersion_` | 480 | 100% |
| `ParentTemplateId` | 480 | 100% |
| `MapKey` | 480 | 100% |
| `Type` | 480 | 100% |
| `Name` | 480 | 100% |
| `LevelName` | 350 | 72.9% |
| `OffsetMin_Bezier3` | 334 | 69.6% |
| `ImpactFX` | 315 | 65.6% |
| `InitialSpeed` | 290 | 60.4% |
| `Flag` | 275 | 57.3% |
| `PhysicsTemplate` | 275 | 57.3% |
| `GroupID` | 275 | 57.3% |
| `CameraOffset` | 275 | 57.3% |
| `VisualTemplate` | 275 | 57.3% |
| `HasGameplayValue` | 273 | 56.9% |
| `PreviewPathImpactFX` | 272 | 56.7% |
| `PreviewPathMaterial` | 270 | 56.2% |
| `CastBone` | 269 | 56% |
| `VelocityMode` | 244 | 50.8% |
| `TrailFX` | 228 | 47.5% |
| `PhysicsOpenTemplate` | 213 | 44.4% |
| `Acceleration` | 213 | 44.4% |
| `ShiftBMin_Bezier4` | 175 | 36.5% |
| `ShiftBMax_Bezier4` | 175 | 36.5% |
| `RotateImpact` | 142 | 29.6% |
| `TrajectoryType` | 132 | 27.5% |
| `GroundImpactFX` | 110 | 22.9% |
| `Speed` | 100 | 20.8% |
| `ShiftMin_Bezier3` | 80 | 16.7% |
| `DetachBeam` | 77 | 16% |
| `NeedsImpactSFX` | 72 | 15% |
| `ImpactSoundResourceID` | 64 | 13.3% |
| `ProjectilePath` | 63 | 13.1% |
| `DestroyTrailFXOnImpact` | 46 | 9.6% |
| `BeamFX` | 42 | 8.8% |
| `PreviewPathRadius` | 33 | 6.9% |
| `LifeTime` | 33 | 6.9% |
| `PathRadius` | 31 | 6.5% |
| `CastShadow` | 26 | 5.4% |
| `RotateMode` | 20 | 4.2% |
| `CurveResourceId` | 18 | 3.8% |
| `OffsetMax_Bezier3` | 14 | 2.9% |
| `PathShift` | 14 | 2.9% |
| `DistanceMin_Bezier3` | 12 | 2.5% |
| `Fadeable` | 12 | 2.5% |
| `FadeIn` | 12 | 2.5% |
| `ShiftMax_Bezier3` | 12 | 2.5% |
| `DistanceMax_Bezier3` | 12 | 2.5% |
| `Scale` | 12 | 2.5% |
| `IgnoreRoof` | 10 | 2.1% |
| `ShiftAMin_Bezier4` | 6 | 1.2% |
| `PathMaxArcDist` | 6 | 1.2% |
| `PathRepeat` | 6 | 1.2% |
| `PathMinArcDist` | 6 | 1.2% |
| `RecieveDecal` | 5 | 1% |
| `ShiftAMax_Bezier4` | 4 | 0.8% |
| `OffsetBMin_Bezier4` | 3 | 0.6% |
| `OffsetAMin_Bezier4` | 3 | 0.6% |
| `OffsetBMax_Bezier4` | 3 | 0.6% |
| `DistanceMax_Bezier4` | 3 | 0.6% |
| `OffsetAMax_Bezier4` | 3 | 0.6% |
| `DistanceMin_Bezier4` | 3 | 0.6% |
| `MaxPathRadius` | 2 | 0.4% |
| `DevComment` | 1 | 0.2% |

## TYPE: light (446 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `Type` | 446 | 100% |
| `MapKey` | 446 | 100% |
| `ParentTemplateId` | 446 | 100% |
| `LevelName` | 446 | 100% |
| `_OriginalFileVersion_` | 446 | 100% |
| `Name` | 446 | 100% |
| `Intensity` | 359 | 80.5% |
| `Radius` | 317 | 71.1% |
| `Color` | 261 | 58.5% |
| `Gain` | 247 | 55.4% |
| `ScatteringScale` | 218 | 48.9% |
| `FlatFalloff` | 202 | 45.3% |
| `Angle` | 202 | 45.3% |
| `Kelvin` | 199 | 44.6% |
| `UseTemperature` | 198 | 44.4% |
| `LightType` | 193 | 43.3% |
| `Amount` | 188 | 42.2% |
| `Shadow` | 187 | 41.9% |
| `DirectionLightDimensions` | 181 | 40.6% |
| `Enabled` | 181 | 40.6% |
| `DirectionLightAttenuationSide` | 172 | 38.6% |
| `DirectionLightAttenuationEnd` | 170 | 38.1% |
| `Speed` | 161 | 36.1% |
| `MovementAmount` | 160 | 35.9% |
| `DirectionLightAttenuationStart` | 158 | 35.4% |
| `MovementSpeed` | 153 | 34.3% |
| `PreExpose` | 152 | 34.1% |
| `IsFlickering` | 150 | 33.6% |
| `IsMoving` | 146 | 32.7% |
| `LightChannelFlag` | 138 | 30.9% |
| `VolumetricShadow` | 135 | 30.3% |
| `PhysicsTemplate` | 118 | 26.5% |
| `Flag` | 118 | 26.5% |
| `CameraOffset` | 118 | 26.5% |
| `VisualTemplate` | 118 | 26.5% |
| `GroupID` | 118 | 26.5% |
| `HasGameplayValue` | 113 | 25.3% |
| `RecieveDecal` | 113 | 25.3% |
| `DirectionLightAttenuationFunction` | 107 | 24% |
| `PhysicsOpenTemplate` | 105 | 23.5% |
| `CastShadow` | 97 | 21.7% |
| `VolumetricLightIntensity` | 16 | 3.6% |
| `VolumetricLightCollisionProbability` | 16 | 3.6% |
| `LightVolume` | 16 | 3.6% |
| `TextureMapping` | 16 | 3.6% |
| `LightVolumeSamplesCount` | 16 | 3.6% |
| `LightCookieTexture` | 12 | 2.7% |
| `Scale` | 3 | 0.7% |
| `RenderChannel` | 2 | 0.4% |
| `DevComment` | 1 | 0.2% |

## TYPE: decal (349 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `LevelName` | 349 | 100% |
| `Name` | 349 | 100% |
| `Type` | 349 | 100% |
| `_OriginalFileVersion_` | 349 | 100% |
| `ParentTemplateId` | 349 | 100% |
| `MapKey` | 349 | 100% |
| `Material` | 346 | 99.1% |
| `Dimensions` | 345 | 98.9% |
| `offset` | 344 | 98.6% |
| `GroupID` | 341 | 97.7% |
| `Tiling` | 341 | 97.7% |
| `NormalBlendingFactor` | 341 | 97.7% |
| `PhysicsTemplate` | 341 | 97.7% |
| `VisualTemplate` | 341 | 97.7% |
| `Flag` | 341 | 97.7% |
| `CameraOffset` | 341 | 97.7% |
| `HasGameplayValue` | 340 | 97.4% |
| `Layer` | 327 | 93.7% |
| `AngleCutoff` | 243 | 69.6% |
| `PhysicsOpenTemplate` | 242 | 69.3% |
| `Opacity` | 166 | 47.6% |
| `UUID` | 114 | 32.7% |
| `DecalType` | 43 | 12.3% |

## TYPE: surface (87 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `ParentTemplateId` | 87 | 100% |
| `MapKey` | 87 | 100% |
| `Name` | 87 | 100% |
| `_OriginalFileVersion_` | 87 | 100% |
| `LevelName` | 87 | 100% |
| `Type` | 87 | 100% |
| `DisplayName` | 81 | 93.1% |
| `DecalMaterial` | 76 | 87.4% |
| `Description` | 71 | 81.6% |
| `GroupID` | 68 | 78.2% |
| `CameraOffset` | 68 | 78.2% |
| `Flag` | 68 | 78.2% |
| `PhysicsTemplate` | 68 | 78.2% |
| `VisualTemplate` | 68 | 78.2% |
| `HasGameplayValue` | 67 | 77% |
| `SurfaceCategory` | 66 | 75.9% |
| `Icon` | 59 | 67.8% |
| `PhysicsOpenTemplate` | 56 | 64.4% |
| `AiPathColor` | 52 | 59.8% |
| `Summon` | 52 | 59.8% |
| `MaterialType` | 46 | 52.9% |
| `FadeOutSpeed` | 36 | 41.4% |
| `RollConditions` | 24 | 27.6% |
| `DefaultLifeTime` | 12 | 13.8% |
| `FadeInSpeed` | 11 | 12.6% |
| `SurfaceGrowTimer` | 9 | 10.3% |
| `SpawnLightTemplateID` | 9 | 10.3% |
| `ObscuredStateOverride` | 8 | 9.2% |
| `SpawnLightRandomVerticalRangeOffset` | 8 | 9.2% |
| `EnableLightSpawning` | 7 | 8% |
| `NormalBlendingFactor` | 7 | 8% |
| `OnEnterDistanceOverride` | 7 | 8% |
| `Scale` | 6 | 6.9% |
| `OnMoveDistanceOverride` | 6 | 6.9% |
| `CanEnterCombat` | 5 | 5.7% |
| `Seed` | 4 | 4.6% |
| `AlwaysUseDefaultLifeTime` | 3 | 3.4% |
| `FallDamageMultiplier` | 3 | 3.4% |
| `CastShadow` | 2 | 2.3% |
| `CanSeeThrough` | 2 | 2.3% |
| `RemoveDestroyedItems` | 1 | 1.1% |
| `RecieveDecal` | 1 | 1.1% |
| `CanShootThrough` | 1 | 1.1% |

## TYPE: CombinedLight (76 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `_OriginalFileVersion_` | 76 | 100% |
| `MapKey` | 76 | 100% |
| `ParentTemplateId` | 76 | 100% |
| `Name` | 76 | 100% |
| `Type` | 76 | 100% |
| `LevelName` | 76 | 100% |
| `GameplayRadius` | 73 | 96.1% |
| `GameplaySpotlightAngle` | 71 | 93.4% |
| `Intensity` | 69 | 90.8% |
| `GameplayDirectionalDimensions` | 69 | 90.8% |
| `IsFlickering` | 68 | 89.5% |
| `FlatFalloff` | 68 | 89.5% |
| `LightCookieResource` | 68 | 89.5% |
| `IsMoving` | 68 | 89.5% |
| `GroupID` | 68 | 89.5% |
| `PhysicsOpenTemplate` | 68 | 89.5% |
| `Flag` | 68 | 89.5% |
| `Angle` | 68 | 89.5% |
| `Radius` | 68 | 89.5% |
| `DirectionLightAttenuationFunction` | 68 | 89.5% |
| `DirectionLightAttenuationStart` | 68 | 89.5% |
| `DirectionLightDimensions` | 68 | 89.5% |
| `MovementSpeed` | 68 | 89.5% |
| `PhysicsTemplate` | 68 | 89.5% |
| `VolumetricShadow` | 68 | 89.5% |
| `LightChannelFlag` | 68 | 89.5% |
| `Gain` | 68 | 89.5% |
| `CameraOffset` | 68 | 89.5% |
| `VisualTemplate` | 68 | 89.5% |
| `Enabled` | 68 | 89.5% |
| `GameplayCheckLOS` | 68 | 89.5% |
| `ScatteringScale` | 68 | 89.5% |
| `HasGameplayValue` | 68 | 89.5% |
| `Shadow` | 68 | 89.5% |
| `PreExpose` | 68 | 89.5% |
| `Color` | 68 | 89.5% |
| `UseTemperature` | 68 | 89.5% |
| `DirectionLightAttenuationSide` | 68 | 89.5% |
| `DirectionLightAttenuationEnd` | 68 | 89.5% |
| `LightType` | 68 | 89.5% |
| `GameplayEdgeSharpening` | 68 | 89.5% |
| `Amount` | 68 | 89.5% |
| `MovementAmount` | 68 | 89.5% |
| `IsHalfLit` | 68 | 89.5% |
| `GameplayIsActive` | 68 | 89.5% |
| `Speed` | 68 | 89.5% |
| `Kelvin` | 68 | 89.5% |
| `RecieveDecal` | 67 | 88.2% |
| `IsSunlight` | 67 | 88.2% |
| `CastShadow` | 67 | 88.2% |
| `LightCookieTexture` | 8 | 10.5% |

## TYPE: trigger (42 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `Type` | 42 | 100% |
| `Name` | 42 | 100% |
| `MapKey` | 42 | 100% |
| `_OriginalFileVersion_` | 42 | 100% |
| `LevelName` | 41 | 97.6% |
| `PhysicsType` | 41 | 97.6% |
| `VisualTemplate` | 39 | 92.9% |
| `CameraOffset` | 39 | 92.9% |
| `Flag` | 39 | 92.9% |
| `GroupID` | 39 | 92.9% |
| `TriggerType` | 39 | 92.9% |
| `TriggerGizmoOverride` | 39 | 92.9% |
| `Color4` | 39 | 92.9% |
| `PhysicsTemplate` | 39 | 92.9% |
| `HasGameplayValue` | 38 | 90.5% |
| `ParentTemplateId` | 30 | 71.4% |
| `PhysicsOpenTemplate` | 26 | 61.9% |
| `Scale` | 25 | 59.5% |
| `GizmoColorOverride` | 24 | 57.1% |
| `UsingGizmoColorOverride` | 24 | 57.1% |
| `HasCustomPoint` | 19 | 45.2% |
| `FadeGroupOnly` | 16 | 38.1% |
| `CustomPointTransform` | 16 | 38.1% |
| `Height` | 12 | 28.6% |
| `Extents` | 12 | 28.6% |
| `CastShadow` | 7 | 16.7% |
| `OnlyOsirisEvents` | 6 | 14.3% |
| `OnlyCharacterEvents` | 5 | 11.9% |
| `RecieveDecal` | 5 | 11.9% |
| `Index` | 4 | 9.5% |
| `EnterEvent` | 3 | 7.1% |
| `EventSendingMode` | 3 | 7.1% |
| `Radius` | 3 | 7.1% |
| `LeaveEvent` | 3 | 7.1% |
| `TriggerCrimeArea` | 2 | 4.8% |
| `MixdownSpeed` | 2 | 4.8% |
| `Angle` | 2 | 4.8% |
| `MixdownDelayTime` | 2 | 4.8% |
| `RenderMethod` | 2 | 4.8% |
| `FadeTime` | 2 | 4.8% |
| `CustomMixRadius` | 1 | 2.4% |
| `GroupSizeMin` | 1 | 2.4% |
| `RegionCameraLock` | 1 | 2.4% |
| `TriggerGameCameraBehavior` | 1 | 2.4% |
| `Occlusion` | 1 | 2.4% |
| `TriggerRegion` | 1 | 2.4% |
| `FOV` | 1 | 2.4% |
| `UseOcclusion` | 1 | 2.4% |
| `GroupSpawnTimeMin` | 1 | 2.4% |
| `Optional` | 1 | 2.4% |
| `Player` | 1 | 2.4% |
| `AuxBus3` | 1 | 2.4% |
| `Team` | 1 | 2.4% |
| `MaxCharacters` | 1 | 2.4% |
| `IsUsingCalculatedSceneBounds` | 1 | 2.4% |
| `Speed` | 1 | 2.4% |
| `StationSound` | 1 | 2.4% |
| `TriggerCameraLockPos` | 1 | 2.4% |
| `Fadeable` | 1 | 2.4% |
| `Zoom` | 1 | 2.4% |
| `MaxAttenuation` | 1 | 2.4% |
| `LevelOverride` | 1 | 2.4% |
| `IsAnchor` | 1 | 2.4% |
| `AreaLevelOverrideGuid` | 1 | 2.4% |
| `OneShotTrigger` | 1 | 2.4% |
| `AuxBus1` | 1 | 2.4% |
| `ExplorationReward` | 1 | 2.4% |
| `AmbientSound` | 1 | 2.4% |
| `CrowdAreItemsAllowed` | 1 | 2.4% |
| `IsWorldTimeline` | 1 | 2.4% |
| `GroupSizeMax` | 1 | 2.4% |
| `RegionCameraLockPos` | 1 | 2.4% |
| `RegionShroudVisibleInWorld` | 1 | 2.4% |
| `AuxBus4` | 1 | 2.4% |
| `Border` | 1 | 2.4% |
| `ShouldPreloadWorldTimelineActors` | 1 | 2.4% |
| `GroupSpawnTimeMax` | 1 | 2.4% |
| `IsRooof` | 1 | 2.4% |
| `CrowdSystemEnabled` | 1 | 2.4% |
| `ParentGUID` | 1 | 2.4% |
| `RegionShroudGen` | 1 | 2.4% |
| `SoundEvent` | 1 | 2.4% |
| `AttenuationScale` | 1 | 2.4% |
| `AuxBus2` | 1 | 2.4% |
| `ParentTrigger` | 1 | 2.4% |
| `StagingType` | 1 | 2.4% |

## TYPE: Schematic (40 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `MapKey` | 40 | 100% |
| `VisualTemplate` | 40 | 100% |
| `PhysicsTemplate` | 40 | 100% |
| `CameraOffset` | 40 | 100% |
| `HasGameplayValue` | 40 | 100% |
| `GroupID` | 40 | 100% |
| `PhysicsOpenTemplate` | 40 | 100% |
| `_OriginalFileVersion_` | 40 | 100% |
| `Type` | 40 | 100% |
| `Flag` | 40 | 100% |
| `Name` | 40 | 100% |
| `ParentTemplateId` | 40 | 100% |
| `LevelName` | 40 | 100% |

## TYPE: fogVolume (7 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `PhysicsOpenTemplate` | 7 | 100% |
| `CameraOffset` | 7 | 100% |
| `_OriginalFileVersion_` | 7 | 100% |
| `Albedo` | 7 | 100% |
| `PhysicsTemplate` | 7 | 100% |
| `GroupID` | 7 | 100% |
| `Type` | 7 | 100% |
| `Radius` | 7 | 100% |
| `Replaces` | 7 | 100% |
| `Flag` | 7 | 100% |
| `MapKey` | 7 | 100% |
| `TransitionDistance` | 7 | 100% |
| `Name` | 7 | 100% |
| `Enabled` | 7 | 100% |
| `VisualTemplate` | 7 | 100% |
| `NoiseWind` | 7 | 100% |
| `NoiseCoverage` | 7 | 100% |
| `ParentTemplateId` | 7 | 100% |
| `LevelName` | 7 | 100% |
| `FogVolumeShape` | 7 | 100% |
| `NoiseFrequency` | 7 | 100% |
| `Density` | 7 | 100% |
| `Size` | 7 | 100% |
| `NoiseRotation` | 7 | 100% |
| `HasGameplayValue` | 7 | 100% |
| `Layer` | 4 | 57.1% |
| `DevComment` | 1 | 14.3% |

## TYPE: SplineConstruction (5 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `VisualTemplate` | 5 | 100% |
| `PhysicsTemplate` | 5 | 100% |
| `Name` | 5 | 100% |
| `CameraOffset` | 5 | 100% |
| `HasGameplayValue` | 5 | 100% |
| `GroupID` | 5 | 100% |
| `MapKey` | 5 | 100% |
| `Type` | 5 | 100% |
| `Flag` | 5 | 100% |
| `ParentTemplateId` | 5 | 100% |
| `LevelName` | 5 | 100% |
| `_OriginalFileVersion_` | 5 | 100% |
| `Scale` | 2 | 40% |

## TYPE: Spline (3 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `GroupID` | 3 | 100% |
| `HasGameplayValue` | 3 | 100% |
| `MapKey` | 3 | 100% |
| `Type` | 3 | 100% |
| `Target` | 3 | 100% |
| `Scale` | 3 | 100% |
| `Speed` | 3 | 100% |
| `CameraOffset` | 3 | 100% |
| `Looping` | 3 | 100% |
| `VisualTemplate` | 3 | 100% |
| `Flag` | 3 | 100% |
| `Name` | 3 | 100% |
| `_OriginalFileVersion_` | 3 | 100% |
| `LevelName` | 3 | 100% |
| `PhysicsTemplate` | 3 | 100% |
| `FOV` | 3 | 100% |
| `DevComment` | 2 | 66.7% |
| `IsPlatformSpline` | 2 | 66.7% |
| `PhysicsOpenTemplate` | 1 | 33.3% |
| `ParentTemplateId` | 1 | 33.3% |
| `IsStraightPath` | 1 | 33.3% |

## TYPE: lightProbe (2 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `Intensity` | 2 | 100% |
| `CameraOffset` | 2 | 100% |
| `LightProbeShape` | 2 | 100% |
| `CaptureType` | 2 | 100% |
| `PhysicsTemplate` | 2 | 100% |
| `GroupID` | 2 | 100% |
| `Name` | 2 | 100% |
| `Radius` | 2 | 100% |
| `Flag` | 2 | 100% |
| `_OriginalFileVersion_` | 2 | 100% |
| `Type` | 2 | 100% |
| `MapKey` | 2 | 100% |
| `InfiniteCapture` | 2 | 100% |
| `VisualTemplate` | 2 | 100% |
| `LightProbeType` | 2 | 100% |
| `LevelName` | 2 | 100% |
| `Enabled` | 2 | 100% |
| `Scale` | 2 | 100% |
| `TransitionDistance` | 2 | 100% |
| `Size` | 2 | 100% |
| `HasGameplayValue` | 2 | 100% |
| `RecieveDecal` | 1 | 50% |
| `CastShadow` | 1 | 50% |
| `ParentTemplateId` | 1 | 50% |
| `TriggerAtmosphere` | 1 | 50% |
| `PhysicsOpenTemplate` | 1 | 50% |
| `TriggerLighting` | 1 | 50% |

## TYPE: constellationHelper (1 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `GroupID` | 1 | 100% |
| `MapKey` | 1 | 100% |
| `VisualTemplate` | 1 | 100% |
| `HasGameplayValue` | 1 | 100% |
| `CastShadow` | 1 | 100% |
| `RecieveDecal` | 1 | 100% |
| `CameraOffset` | 1 | 100% |
| `PhysicsTemplate` | 1 | 100% |
| `_OriginalFileVersion_` | 1 | 100% |
| `Type` | 1 | 100% |
| `Flag` | 1 | 100% |
| `LevelName` | 1 | 100% |
| `PhysicsOpenTemplate` | 1 | 100% |
| `Name` | 1 | 100% |
| `ParentTemplateId` | 1 | 100% |

## TYPE: constellation (1 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `VisualTemplate` | 1 | 100% |
| `PhysicsTemplate` | 1 | 100% |
| `PhysicsOpenTemplate` | 1 | 100% |
| `MapKey` | 1 | 100% |
| `CameraOffset` | 1 | 100% |
| `HasGameplayValue` | 1 | 100% |
| `GroupID` | 1 | 100% |
| `_OriginalFileVersion_` | 1 | 100% |
| `Type` | 1 | 100% |
| `Flag` | 1 | 100% |
| `LevelName` | 1 | 100% |
| `Name` | 1 | 100% |
| `ParentTemplateId` | 1 | 100% |
| `DevComment` | 1 | 100% |

## TYPE: terrain (1 nodes)

| Attribute | Count | % |
|-----------|-------|---|
| `Scale` | 1 | 100% |
| `VisualTemplate` | 1 | 100% |
| `PhysicsTemplate` | 1 | 100% |
| `CameraOffset` | 1 | 100% |
| `HasGameplayValue` | 1 | 100% |
| `GroupID` | 1 | 100% |
| `Type` | 1 | 100% |
| `Flag` | 1 | 100% |
| `MapKey` | 1 | 100% |
| `Name` | 1 | 100% |
| `LevelName` | 1 | 100% |
| `_OriginalFileVersion_` | 1 | 100% |


