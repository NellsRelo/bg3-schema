# GameObjects Attribute Scan: _merged.lsx
# Total nodes: 1252
# Types: 13

## ALL UNIQUE ATTRIBUTES (286 total)

| Attribute | Type | Total Count | In Types | Examples |
|-----------|------|-------------|----------|----------|
| `_OriginalFileVersion_` | int64 | 1252 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `Acceleration` | float | 4 | projectile | -5 / 0 / 7 |
| `ActivationGroupId` | FixedString | 1 | character | WLD_FOR_GnomeGoblins |
| `ActiveCharacterLightID` | FixedString | 6 | character | 233033a1-b43a-4ad9-976a-8a062b345e21 / e278f6a0-26d7-49be-b11a-9b84bc313c3c / 13fa34e1-78ae-4d49-a69b-3a1f3987e53b |
| `AiHint` | guid | 41 | character, item | 00000000-0000-0000-0000-000000000000 / f76e60e1-2957-470b-8a25-efdf32475ce0 / f5614548-32cc-4e2e-b108-32e5d532471e |
| `AllowSummonTeleport` | bool | 1 | item | True |
| `Amount` | float | 7 | CombinedLight, light | 0 / 3000 |
| `Angle` | fvec2 | 17 | CombinedLight, light | 35 45 / 35 60 |
| `AngleCutoff` | float | 1 | decal | 0.8 |
| `AnimationSetResourceID` | FixedString | 62 | character | bbf6ee33-3328-946a-9b9f-872f0624e15d / 480f4da3-8e32-ce07-5a00-a233bcf602d9 / 83c01830-8e60-035c-c6b1-51bb2f81a32d |
| `AnubisConfigName` | FixedString | 59 | character, item | DefaultMonster / PLA_PersistentFlame / FOR_MeltingFurnace |
| `Archetype` | FixedString | 40 | character, item | base / mage / imp_melee |
| `AttackableWhenClickThrough` | bool | 12 | item | False |
| `BloodSurfaceType` | FixedString | 33 | character, item | SurfaceNone / SurfaceBlood / SurfacePoison |
| `BloodType` | FixedString | 11 | character | Red / Green |
| `BookType` | uint8 | 2 | item | 3 |
| `Border` | float | 1 | trigger | 0.5 |
| `CameraOffset` | fvec3 | 318 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | 0 0 0 |
| `CanBeImprovisedWeapon` | bool | 1 | item | True |
| `CanBeMoved` | bool | 26 | item | False / True |
| `CanBePickedUp` | bool | 26 | character, item | True / False |
| `CanBeTeleported` | bool | 1 | character | True |
| `CanClickThrough` | bool | 90 | item, scenery | False / True |
| `CanClimbLadders` | bool | 3 | character | False / True |
| `CanClimbOn` | bool | 178 | item, scenery | False / True |
| `CanFight` | bool | 6 | character, item | True / False |
| `CanJoinCombat` | bool | 9 | character, item | False |
| `CanOpenDoors` | bool | 1 | character | False |
| `CanShootThrough` | bool | 154 | item, scenery | True / False |
| `CaptureType` | uint8 | 1 | lightProbe | 2 |
| `CastBone` | FixedString | 6 | projectile | Dummy_CastFX / Cast_FX / Dummy_Root |
| `CastShadow` | bool | 17 | CombinedLight, item, light, lightProbe, projectile, scenery | False |
| `CharacterVisualResourceID` | FixedString | 139 | character | 7a7a65c4-7590-e5bf-7cb7-09a8573c73fa / 91fcb6a4-bf5f-2a3c-f538-8924593a644c / f3b06680-b2a2-e8a0-925d-9378bbb08360 |
| `Color` | fvec3 | 6 | CombinedLight, light | 1 1 1 / 1 0.9411765 0.8627451 |
| `Color4` | fvec4 | 4 | trigger | 0.25 0 0 1 |
| `ColorPreset` | guid | 1 | item | 68d055b3-c3df-ab42-857d-cfe747e4a85b |
| `CombatGroupID` | FixedString | 5 | character | 567b5ad7-687c-ca8f-3763-e21195a99d00 / b8945d7f-7a8d-ab9a-0a47-63b124322028 |
| `CombatName` | LSString | 3 | character | S_GOB_Goblin_INT_King_01 / S_GOB_Checkpoint_Goblin_Melee_01 / S_FOR_Gnome_Goblin_Melee_01 |
| `ConstellationConfigName` | FixedString | 2 | item | FallingStalactite |
| `CoverAmount` | uint8 | 209 | item, scenery | 0 / 1 |
| `CriticalHitType` | FixedString | 2 | character | Default |
| `CustomPointTransform` | mat4x4 | 3 | trigger |  1.00  0.00  0.00  0.00 &#xD;&#xA; 0.00  1.00  0.00  0.00 &#xD;&#xA; 0.00  0.00  1.00  0.00 &#xD;&#xA; 0.00  0.00  0.00  1.00 &#xD;&#xA; |
| `DeathEffect` | guid | 7 | character | 9e156f86-4b68-4d8b-a282-f6ee24dd7819 / eb0aa43b-fcdc-4ef2-8c54-f60e75074e83 / 00000000-0000-0000-0000-000000000000 |
| `DeathRaycastMaxLength` | float | 8 | character | 1.5 / 1 |
| `DefaultState` | FixedString | 6 | item | open / closed |
| `DefaultState` | uint8 | 1 | character | 11 |
| `Description` | TranslatedString | 223 | item |  |
| `Destroyed` | bool | 15 | item | True |
| `DetachBeam` | bool | 1 | projectile | True |
| `DevComment` | LSString | 10 | character, item | |NPC used to introduce oathbreaker to paladins| / Shouldn't be a stone tablets - referred to as a book in dialog / The Hag's human form (disguised with illusion, so mechanically still a hag) |
| `Dimensions` | fvec3 | 5 | decal | 1 1 1 |
| `DirectionLightAttenuationEnd` | float | 16 | CombinedLight, light | 1.5 / 1 / 0 |
| `DirectionLightAttenuationFunction` | uint8 | 6 | CombinedLight, light | 2 |
| `DirectionLightAttenuationSide` | float | 16 | CombinedLight, light | 1.7 / 1 / 0 |
| `DirectionLightAttenuationStart` | float | 16 | CombinedLight, light | 0.2 / 1 / 0 |
| `DirectionLightDimensions` | fvec3 | 15 | CombinedLight, light | 2.5 3.5 3 / 2.8 4 3 / 1 1 1 |
| `DisableEquipping` | bool | 6 | character | True |
| `DisarmDifficultyClassID` | guid | 2 | item | 831e1fbe-428d-4f4d-bd17-4206d6efea35 |
| `DisintegratedResourceID` | FixedString | 5 | character | c201a86a-297f-4d0d-16a3-073c1098767b / a8df0d5a-d171-89d2-fd37-424a7f914ec6 |
| `DisplayName` | TranslatedString | 597 | character, item, scenery |  |
| `DropSound` | FixedString | 19 | item | fef7023c-75c1-6d74-0668-4e5ab2eb59e4 / 8891f42c-f66e-b87a-d0b7-6f2de68489a8 / 23c6ee88-e1ae-88e5-71d5-b127b60f68ee |
| `Enabled` | bool | 7 | CombinedLight, light, lightProbe | True |
| `Equipment` | FixedString | 76 | character | EQP_Daisy / EQ_Laezel / EQP_Greatsword |
| `EquipmentRace` | guid | 38 | character | 00000000-0000-0000-0000-000000000000 / 47c0315c-7dc6-4862-b39b-8bf3a10f8b54 / cf421f4e-107b-4ae6-86aa-090419c624a5 |
| `EquipmentTypeID` | guid | 13 | item | 12b80df8-aaf1-4543-84fa-c44622e451b5 / 00000000-0000-0000-0000-000000000000 / 62ff4f7c-0724-43fa-997b-ef0c486a5573 |
| `EquipSound` | FixedString | 6 | item | c0c9b3e7-b3bc-2cbc-9de5-0a148cb098cc / 92550df7-e13e-4474-8a7e-a59825eaa805 / 4be7393e-909d-af74-1d02-85caf412cac4 |
| `ExamineRotation` | fvec3 | 9 | item | 65 180 0 / 75 180 0 / 65 18 0 |
| `ExplodedResourceID` | FixedString | 4 | character | 9b371eaa-2ebe-028e-d577-2202ab7acff1 / a8df0d5a-d171-89d2-fd37-424a7f914ec6 / c201a86a-297f-4d0d-16a3-073c1098767b |
| `Extents` | fvec3 | 4 | trigger | 1 1 1 |
| `Faction` | guid | 87 | character, item | 00000000-0000-0000-0000-000000000000 / cfb709b3-220f-9682-bcfb-6f0d8837462e / e7613afc-2775-22c5-9d37-e07a9bbea429 |
| `Fadeable` | bool | 11 | item, scenery, trigger | True |
| `FadeGroupOnly` | bool | 3 | trigger | False |
| `FadeIn` | bool | 1 | item | True |
| `Flag` | int32 | 425 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | 0 |
| `Flag` | uint8 | 2 | item, LevelTemplate | 0 |
| `FlatFalloff` | bool | 16 | CombinedLight, light | False / True |
| `Floating` | bool | 1 | item | True |
| `FoleyLongResourceID` | FixedString | 5 | character | 4bb9b3aa-3c20-7f72-542c-62274ab76f3e |
| `FoleyMediumResourceID` | FixedString | 1 | character | 25c4bf99-7b6e-321c-8aac-e56404796f32 |
| `FoleyShortResourceID` | FixedString | 5 | character | 2363878c-1578-7bc2-b12e-0ba55be1c025 |
| `FreezeGravity` | bool | 3 | item | False / True |
| `Gain` | float | 15 | CombinedLight, light | 2 / 3.5 / 1 |
| `GameplayCheckLOS` | bool | 2 | CombinedLight | False |
| `GameplayDirectionalDimensions` | fvec3 | 2 | CombinedLight | 1 1 1 |
| `GameplayEdgeSharpening` | float | 2 | CombinedLight | 0 |
| `GameplayIsActive` | bool | 2 | CombinedLight | True |
| `GameplayRadius` | float | 2 | CombinedLight | 6 |
| `GameplaySpotlightAngle` | float | 2 | CombinedLight | 40 |
| `GeneratePortrait` | LSString | 40 | character | Icon_Quasit / Icon_Origin_Laezel / Icon_Origin_Wyll |
| `GizmoColorOverride` | fvec4 | 4 | trigger | 0 0 0.25 1 / 0.5 0.5 0.5 0.5 |
| `GravityType` | uint8 | 9 | item | 1 / 0 |
| `GroupID` | uint32 | 318 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | 0 / 7064 |
| `HasCustomPoint` | bool | 4 | trigger | False |
| `HasGameplayValue` | bool | 316 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | False |
| `HiddenFromMinimapRendering` | bool | 1 | TileConstruction | True |
| `HierarchyOnlyFade` | bool | 10 | item, scenery | True |
| `Hostile` | bool | 2 | item | True |
| `Icon` | FixedString | 439 | character, item | 7a7a65c4-7590-e5bf-7cb7-09a8573c73fa-_(Icon_Quasit) / Item_DEN_VoloOperation_ErsatzEye / Item_DEC_Goblins_Camp_CookingPot_A_Poisoned |
| `IgnoreGenerics` | bool | 1 | item | True |
| `ImpactFX` | FixedString | 8 | projectile | VFX_Script_UND_AdamantineForge_Spark_01 / VFX_Projectiles_Force_Trap_Impact_01 / VFX_Projectiles_Nere_PsychicMirror_Explosion_Impact_01 |
| `ImpactSound` | FixedString | 40 | item | d44f2631-ebea-49ff-79ba-415636e0270a / 80788119-e116-0b2b-6e33-92d15eaf3bcc / fa6145a3-f95d-60a9-9583-ba601bc3a583 |
| `InfiniteCapture` | bool | 1 | lightProbe | True |
| `InitialSpeed` | float | 9 | projectile | 18 / 10 / 30 |
| `Intensity` | float | 19 | CombinedLight, light, lightProbe | 2 / 3000 / 3 |
| `InteractionFilterType` | uint8 | 3 | item | 2 |
| `InventoryMoveSound` | FixedString | 17 | item | fef7023c-75c1-6d74-0668-4e5ab2eb59e4 / 8891f42c-f66e-b87a-d0b7-6f2de68489a8 / 23c6ee88-e1ae-88e5-71d5-b127b60f68ee |
| `InventoryType` | uint8 | 30 | character, item | 14 / 9 / 11 |
| `IsBlueprintDisabledByDefault` | bool | 8 | item | False |
| `IsBoss` | bool | 4 | character | True |
| `IsCinematic` | bool | 6 | LevelTemplate | False |
| `IsDecorative` | bool | 2 | item, scenery | True |
| `IsDynamicLayer` | bool | 31 | LevelTemplate | False |
| `IsEquipmentLootable` | bool | 9 | character | False / True |
| `IsFlickering` | bool | 6 | CombinedLight, light | False |
| `IsHalfLit` | bool | 2 | CombinedLight | False |
| `IsInspector` | bool | 47 | item | False / True |
| `IsInteractionDisabled` | bool | 4 | item | True |
| `IsLootable` | bool | 9 | character | False / True |
| `IsMoving` | bool | 64 | CombinedLight, LevelTemplate, light | False / True |
| `IsPlatformOwner` | bool | 2 | item | True |
| `IsPointerBlocker` | bool | 73 | item | False |
| `IsPortal` | bool | 14 | item | False |
| `IsPortalProhibitedToPlayers` | bool | 1 | item | True |
| `IsPublicDomain` | bool | 2 | item | True |
| `IsRooof` | bool | 1 | trigger | False |
| `IsScrollingObject` | bool | 67 | LevelTemplate | False / True |
| `IsSunlight` | bool | 2 | CombinedLight | False |
| `IsSurfaceBlocker` | bool | 2 | item | True |
| `IsSurfaceCloudBlocker` | bool | 1 | item | True |
| `IsTrap` | bool | 1 | item | True |
| `Kelvin` | float | 7 | CombinedLight, light | 6400 / 2800 / 4800 |
| `Key` | FixedString | 1 | item | UND_SeluneOutpost_Key |
| `LadderAttachOffset` | float | 7 | character | 0 |
| `LadderAttachSpeed` | float | 1 | character | 3 |
| `LadderDetachSpeed` | float | 1 | character | 2.5 |
| `LadderLoopSpeed` | float | 10 | character | 6 / 3.75 / 3 |
| `Layer` | uint32 | 5 | decal | 0 |
| `LevelName` | FixedString | 1250 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger |  |
| `LevelOverride` | int32 | 52 | character, item | -1 / 4 / 0 |
| `LevelTemplateType` | uint8 | 41 | LevelTemplate | 0 / 1 |
| `LifeTime` | float | 1 | projectile | 15 |
| `LightChannel` | uint8 | 10 | character | 5 / 0 |
| `LightChannelFlag` | uint8 | 6 | CombinedLight, light | 191 / 32 |
| `LightCookieResource` | FixedString | 2 | CombinedLight |  |
| `LightID` | FixedString | 13 | character | 71749d1d-9b39-46c3-846d-9f342dc27b36 / 362270fc-bf6b-4603-bb8a-6deebbcca47b / 3faa1c66-5d35-4e87-868e-d124168b660f |
| `LightProbeShape` | uint8 | 1 | lightProbe | 0 |
| `LightProbeType` | uint8 | 1 | lightProbe | 1 |
| `LightType` | uint8 | 17 | CombinedLight, light | 2 / 0 |
| `LightVolume` | bool | 1 | light | False |
| `LightVolumeSamplesCount` | int32 | 1 | light | 1024 |
| `LoopSound` | FixedString | 89 | item, scenery | edab4cf9-5637-fa0e-43fe-49305c5a3218 / 14523ac7-8dbc-4d82-0deb-92ff37d92954 / 92182f4d-e6e8-1022-0ee2-8df5446bf303 |
| `MapKey` | FixedString | 1252 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Material` | FixedString | 5 | decal | 7ea41503-e23f-d7ce-3aec-49d396a74297 / 21ecd5b6-4b42-f191-b148-a2534b18307d / f8bc6b1b-f055-439b-e273-44a6e3ebd90d |
| `maxStackAmount` | int32 | 30 | item | 1 / 100 / 99 |
| `MeshProxy` | FixedString | 17 | item | 3f38bcda-21ee-66bb-3c6d-be241a1df6f0 |
| `MovablePlatformStartSound` | FixedString | 26 | LevelTemplate | 9d4f53f9-83bd-8d55-6560-16bf23e21154 / b2802ca6-a2ac-9f2f-927c-c8bfbcb5b00d / 85018e75-1504-9afc-f4b4-fe1a3210d329 |
| `MovablePlatformStopSound` | FixedString | 26 | LevelTemplate | 54604628-1d45-5ae0-95e9-ddb97e905137 / 76d64a2f-9f86-70c8-f483-da305eb0f11f / c9917b16-72ed-33da-0a7f-7d079a443887 |
| `MovementAmount` | float | 6 | CombinedLight, light | 0 / 0.15 |
| `MovementSpeed` | float | 6 | CombinedLight, light | 0 / 5 |
| `Name` | LSString | 1252 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `NormalBlendingFactor` | float | 5 | decal | 0 |
| `offset` | fvec2 | 5 | decal | 0 0 |
| `OffsetMin_Bezier3` | fvec2 | 4 | projectile | 0 1 / 0 10 / 0 1.5 |
| `OneShotTrigger` | bool | 1 | trigger | False |
| `OnlyCharacterEvents` | bool | 1 | trigger | False |
| `OnlyOsirisEvents` | bool | 1 | trigger | False |
| `OnUseDescription` | TranslatedString | 8 | item |  |
| `Opacity` | float | 11 | decal, item | 0 / 1 |
| `ParentTemplateId` | FixedString | 1248 | character, CombinedLight, decal, item, LevelTemplate, light, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PathRepeat` | uint32 | 1 | projectile | 2 |
| `Persistent` | bool | 72 | LevelTemplate | False |
| `PhysicsCollisionSound` | FixedString | 1 | item | 0c130d61-2b03-3abb-2d1d-3ea22eb35034 |
| `PhysicsOpenTemplate` | FixedString | 144 | character, CombinedLight, decal, item, LevelTemplate, light, prefab, projectile, scenery, TileConstruction, trigger | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 891 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `PhysicsType` | int32 | 4 | trigger | 2 |
| `PickupSound` | FixedString | 21 | item | c87e342d-a717-4d86-c15a-6c0c7d9520c1 / 0c6e22db-8de7-919a-88c3-79532bca7898 / 06cee190-7109-18f2-8c2e-6eedc1eff4b2 |
| `PortraitVisualResourceID` | FixedString | 17 | character | 685e521d-a4a8-0199-1064-05840a43d28e / 252f4a0d-d502-0985-52f2-973c38377faa / bae88ae9-0be4-cb47-5a1d-3a25b7bbf5e3 |
| `PreExpose` | bool | 6 | CombinedLight, light | True / False |
| `PreviewPathImpactFX` | FixedString | 4 | projectile | VFX_UI_DestinationBeam_Projectile_01 |
| `PreviewPathMaterial` | FixedString | 4 | projectile | 312a1494-a0e2-c215-cf51-bda58a6b2341 |
| `ProjectilePath` | uint8 | 3 | projectile | 3 / 0 |
| `Race` | guid | 20 | character | 99c33978-f236-4f5b-a8d8-59aeeaf6140f / b6dccbed-30f3-424b-a181-c4540cf38197 / 02e5c59e-80e7-4176-a289-1d08699583f5 |
| `Race` | int8 | 3 | item | -1 / 2 |
| `Radius` | float | 16 | CombinedLight, light, lightProbe | 2 / 6 / 16 |
| `RagdollTemplate` | FixedString | 1 | character | f6806630-a618-9b15-2c46-8c99f7428bd8 |
| `ReadinessFlags` | uint32 | 289 | character, item, scenery | 128 / 132 / 12 |
| `RecieveDecal` | bool | 47 | character, CombinedLight, item, light, lightProbe, scenery | False / True |
| `RenderMethod` | uint8 | 2 | trigger | 1 |
| `RotateImpact` | bool | 6 | projectile | False / True |
| `Scale` | float | 26 | character, item, LevelTemplate, lightProbe, prefab, SplineConstruction | 1 / 1.45 / 1.1 |
| `ScatteringScale` | float | 16 | CombinedLight, light | 0 / 1 / 3 |
| `ScrollingDirection` | fvec3 | 67 | LevelTemplate | 1 0 0 |
| `ScrollingDistance` | float | 67 | LevelTemplate | 0 / 12000 |
| `ScrollingOffset` | float | 64 | LevelTemplate | 0 |
| `ScrollingOrigin` | fvec3 | 56 | LevelTemplate | 0 0 0 / 0 -230 0 |
| `ScrollingSpeed` | float | 67 | LevelTemplate | 0 / 200 |
| `SeeThrough` | bool | 6 | item, scenery | True |
| `Shadow` | bool | 6 | CombinedLight, light | False / True |
| `ShiftBMax_Bezier4` | float | 3 | projectile | 0.25 |
| `ShiftBMin_Bezier4` | float | 3 | projectile | 0.25 |
| `ShiftMin_Bezier3` | float | 1 | projectile | 0.5 |
| `ShootThroughType` | int8 | 11 | item | 6 / -1 |
| `ShowAttachedSpellDescriptions` | bool | 4 | item | True |
| `Size` | fvec3 | 1 | lightProbe | 10 10 10 |
| `SoftBodyCollisionTemplate` | FixedString | 4 | character | 4350b66a-f56a-4f2a-9c60-b5a56609afa4 / 00000000-0000-0000-0000-000000000000 |
| `SoundActivationRange` | float | 8 | LevelTemplate | -1 |
| `SoundAttenuation` | int16 | 80 | character, item | -1 / 200 / 40 |
| `SoundInitEvent` | FixedString | 77 | character, item | 53a5a5a9-d9e1-8375-28e2-c5958cf15df6 / 084a5647-4331-9c43-9bfe-3bb1d36258f1 |
| `SoundMovementStartEvent` | FixedString | 4 | character | 588ebb89-e66c-4b69-94c8-ba4ac2cc0eab |
| `SoundMovementStopEvent` | FixedString | 5 | character | d7d5091b-f262-44f2-6296-0099f0baac88 / 09320763-a194-028f-77e7-44c287937394 |
| `SoundObjectIndex` | uint8 | 2 | character | 0 |
| `SpeakerGroup` | LSString | 1 | item | 69b61817-8458-47ac-8e78-5e855b0999ab |
| `Speed` | float | 10 | CombinedLight, light, projectile | 18 / 0 / 10 |
| `SpellSet` | FixedString | 39 | character | CommonSummonActions / CommonPlayerActions / CommonNPCActions |
| `StartingActive` | bool | 113 | LevelTemplate | False / True |
| `StartingLoaded` | bool | 68 | LevelTemplate | True |
| `Stats` | FixedString | 382 | character, item | FOR_QuasitSummon / UNI_Volo_ErsatzEye / QUEST_GOB_GoblinBoozeTub_Poisoned |
| `StoryItem` | bool | 18 | item | False / True |
| `SubLevelName` | FixedString | 113 | LevelTemplate | PLT_Underdark_TeleportPlatform / WLD_OwlbearCave_B / WLD_DenSubs_B |
| `SwarmGroup` | FixedString | 1 | character | PLA_Newborn_Gnolls |
| `TechnicalDescription` | TranslatedString | 22 | item |  |
| `TechnicalDescriptionParams` | LSString | 1 | item | 2 |
| `TemplateAfterDestruction` | FixedString | 84 | LevelTemplate | 10f3bc44-31e2-4bb5-b200-fd9eb9a2c36f / 091931ef-6640-43fa-8772-b656c1c5a539 / 9da1f1a5-de4e-4092-ab0a-1a424a1bbd7e |
| `TemplateName` | FixedString | 4 | item |  |
| `TextureMapping` | uint8 | 1 | light | 0 |
| `Tiling` | fvec2 | 5 | decal | 1 1 |
| `Title` | TranslatedString | 9 | character |  |
| `Tooltip` | uint8 | 65 | item | 1 / 2 / 0 |
| `TrailFX` | FixedString | 1 | projectile | VFX_Projectiles_UND_SharFort_Turret_01 |
| `TrajectoryType` | uint8 | 6 | projectile | 0 |
| `TransitionDistance` | float | 1 | lightProbe | 1 |
| `TreasureOnDestroy` | bool | 66 | item | False / True |
| `TriggerAtmosphere` | FixedString | 1 | lightProbe |  |
| `TriggerGizmoOverride` | FixedString | 4 | trigger |  |
| `TriggerType` | FixedString | 4 | trigger | FloorTrigger / RoomTrigger / PortalTrigger |
| `Type` | FixedString | 1252 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | item / character / LevelTemplate |
| `UnequipSound` | FixedString | 4 | item | f69d46c0-213b-038a-5281-9533b61dca7b / 61e89d62-d151-afb2-5c0f-6420a72debfb |
| `Unimportant` | bool | 3 | item | True |
| `UnknownDescription` | TranslatedString | 3 | item |  |
| `UnknownDisplayName` | TranslatedString | 2 | item |  |
| `UseOcclusion` | bool | 2 | character | False |
| `UseSound` | FixedString | 7 | item | 10a8b532-de0b-616e-ffc5-006fcefa8d05 / 817b988e-3cc1-78e6-54bc-45da77580f54 / 434c976d-41d7-3f61-c3fd-f62ffcf2a59e |
| `UseSoundClustering` | bool | 2 | character | False |
| `UseSoundOcclusion` | bool | 12 | LevelTemplate | True |
| `UseTemperature` | bool | 12 | CombinedLight, light | True / False |
| `UsingGizmoColorOverride` | bool | 4 | trigger | False |
| `UUID` | FixedString | 4 | decal |  |
| `VelocityMode` | uint8 | 6 | projectile | 1 / 0 |
| `VFXScale` | float | 1 | character | 1.05 |
| `VisualTemplate` | FixedString | 938 | character, CombinedLight, decal, item, LevelTemplate, light, lightProbe, prefab, projectile, scenery, SplineConstruction, TileConstruction, trigger | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |
| `VocalAlertResourceID` | FixedString | 10 | character | dd97f11e-97e6-ca62-4927-d451ea908606 / 4d987717-c289-ef72-a31d-1851cb2fe023 / 2ebebd33-596f-edea-a781-24177c129887 |
| `VocalAngryResourceID` | FixedString | 7 | character | 7ad6c6ed-f48f-4337-140d-eb274efaa5e7 / 650bf105-11ee-fde9-f41d-5dcfda83871d / 95eb4ea2-a766-db0d-cb1d-0ed5a4e1bf3b |
| `VocalAnticipationResourceID` | FixedString | 4 | character | f978a189-ed06-fdf5-6ec3-4df585c42997 / 00000000-0000-0000-0000-000000000000 / c42a6e98-cb63-e95a-836d-a92f21c491b0 |
| `VocalAttackResourceID` | FixedString | 14 | character | f91093dc-9cff-6209-c339-1f989cfeb57c / 40ea1faa-fa18-438c-a7de-e6502fb2e432 / 2453885e-6382-66d8-91a9-f73b8c03c1f5 |
| `VocalAwakeResourceID` | FixedString | 6 | character | b0456735-95f9-3cd2-f76f-9ad1d3676589 / a8d9d28d-2248-a1c0-93ae-8a0626cfcdda / ed05e7e9-d1a5-95eb-9a80-b83df63072be |
| `VocalBoredResourceID` | FixedString | 7 | character | 93080f52-6904-df3f-fc08-ef56ea2ce95e / 6e6aca73-3d17-33ec-7a12-0ee713dd839f / 4c7e170d-c456-8c04-cd87-75d8d64e0253 |
| `VocalBuffResourceID` | FixedString | 3 | character | 2b09134f-ca11-cadc-d13d-1687db994c33 |
| `VocalDeathResourceID` | FixedString | 13 | character | 0cd61230-6240-7606-abaf-dd5c367e1390 / edfc65a1-a99c-417f-9c88-898bcce0a33e / b586f789-d290-f56a-f7c2-3a8a39f71b53 |
| `VocalDodgeResourceID` | FixedString | 14 | character | d78e413e-87b0-e2d7-1fa7-ab49f489d17b / 6f2fd945-10df-4009-badc-bb065ed95fc8 / e92ad90d-7a5a-078c-df05-3b76d36b4625 |
| `VocalEffortsResourceID` | FixedString | 7 | character | db93489e-d406-4d32-941e-6822c4e6d6d8 / 8b490065-b8c0-653c-be0a-88c2d94e567c / e1187b65-7e87-5c0a-446e-48868b4f994a |
| `VocalExhaustedResourceID` | FixedString | 7 | character | 02d91176-e12f-29df-3a08-746c765d69a1 / fc26a2a3-4275-6773-218a-e906054cc682 / 4518569a-8be5-a76a-0890-720abb37bb2b |
| `VocalFallResourceID` | FixedString | 10 | character | d22569e3-ef14-b831-7194-5467412b3f8e / 9acac199-393d-c188-8409-3516c2e29460 |
| `VocalGaspResourceID` | FixedString | 1 | character | 1896ec0d-e17b-bc47-b994-d77cad0f66b9 |
| `VocalIdle1ResourceID` | FixedString | 2 | character | fc424747-71f7-4828-84d5-95a1d2eae8ae / 6e39843c-842f-ef81-b6e1-608ed7f07662 |
| `VocalIdle2ResourceID` | FixedString | 2 | character | 30c50c6f-f98b-8369-d429-b6b678042107 / f240303e-820c-27f3-cc33-f34c9b1e0292 |
| `VocalIdle3ResourceID` | FixedString | 2 | character | 586f0e98-13e5-e173-2923-0ef3a588eedf / 01b2f23e-b3a2-fa21-c7d4-690cf5c33f7c |
| `VocalInitiativeResourceID` | FixedString | 8 | character | 03a4c740-2a38-de7a-597c-eade8a143849 / 5452daf7-a301-c8b0-4364-428e2841f7f4 / f5d397ca-1ab6-a4a7-a802-9a9305da6ab5 |
| `VocalLaughterManiacalResourceID` | FixedString | 13 | character | df225c8c-e5fd-4788-b47c-c33b97ccdc3a |
| `VocalLaughterResourceID` | FixedString | 15 | character | 2b3255d8-a94d-4ae7-8915-c7236d275543 / 0a2990d7-4b6a-46dc-cab5-b98eb6c8e981 |
| `VocalNoneResourceID` | FixedString | 1 | character | 2af5ab18-2087-45c6-94a8-a968190d618a |
| `VocalPainResourceID` | FixedString | 14 | character | 1477f078-24e7-1295-bca1-fd216b0c253b / 2fdbf6c6-72c6-43a4-8001-0d4b5a74ed52 / af25e1e5-8c5f-c369-a3d4-f88818675815 |
| `VocalRebornResourceID` | FixedString | 2 | character | d32a7f46-7e67-ab71-e5b9-e313c07ea4ba / 293fa315-95db-60ee-64ea-e111b8d649aa |
| `VocalRecoverResourceID` | FixedString | 7 | character | c7757a75-4a39-0de2-c186-b924ae8f4236 / 1a1ebc76-0465-ae45-9ab9-1719ae46acb1 |
| `VocalRelaxedResourceID` | FixedString | 9 | character | 3001e2b0-7803-2244-1fba-b4bf06c02f38 / cbea5af8-dc96-2eb1-b0d1-24f2421b29aa / f7d73a55-e753-ccb5-05c5-6bf71b8f2653 |
| `VocalShoutResourceID` | FixedString | 10 | character | e6ab04ec-6206-9b30-8124-a4b3e6de11a4 / f178cfbf-8331-d81c-f383-230cff46429c |
| `VocalSnoreResourceID` | FixedString | 8 | character | 1c3322b0-d250-df48-63a1-c12931b579ca / edfd660d-a788-380a-ac21-b4f77b008a4c / 7a65e103-2dac-7a09-fb82-c6ff18f4d7bc |
| `VocalSpawnResourceID` | FixedString | 7 | character | d32a7f46-7e67-ab71-e5b9-e313c07ea4ba / f6e2e96e-3820-c546-348a-b26d19246058 / 582c99aa-307e-e008-ccc7-91c87792c3b1 |
| `VocalVictoryResourceID` | FixedString | 14 | character | 670ff92e-b91e-44d6-d328-763a656f4db8 / 4733fa3b-43d1-977b-ad32-611e0408d2ad / 51994cfd-7015-7f9d-7222-2a291218b594 |
| `VocalWeakResourceID` | FixedString | 11 | character | 71e8e323-202e-fe83-fcb3-4d0770739e30 / aac800d0-d1fe-cdd3-84bd-184029dff377 / 377cbb98-e1e4-5521-e0ca-c9bc87c4c922 |
| `VolumetricLightCollisionProbability` | float | 1 | light | 0.0001 |
| `VolumetricLightIntensity` | float | 1 | light | 5000 |
| `VolumetricShadow` | bool | 5 | CombinedLight, light | False / True |
| `Wadable` | bool | 66 | item, scenery | False / True |
| `WadableSurfaceType` | FixedString | 3 | item | SurfaceDeepWater |
| `WalkOn` | bool | 159 | item, scenery | False / True |
| `WalkThrough` | bool | 146 | item, scenery | True / False |

## PER-TYPE BREAKDOWN

### Type: `character` (155 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 155 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `ActivationGroupId` | FixedString | 1 (0.6%) | rare | WLD_FOR_GnomeGoblins |
| `ActiveCharacterLightID` | FixedString | 6 (3.9%) | rare | 233033a1-b43a-4ad9-976a-8a062b345e21 / e278f6a0-26d7-49be-b11a-9b84bc313c3c / 13fa34e1-78ae-4d49-a69b-3a1f3987e53b |
| `AiHint` | guid | 25 (16.1%) | rare | 00000000-0000-0000-0000-000000000000 / f76e60e1-2957-470b-8a25-efdf32475ce0 / f5614548-32cc-4e2e-b108-32e5d532471e |
| `AnimationSetResourceID` | FixedString | 62 (40%) | sparse | bbf6ee33-3328-946a-9b9f-872f0624e15d / 480f4da3-8e32-ce07-5a00-a233bcf602d9 / 83c01830-8e60-035c-c6b1-51bb2f81a32d |
| `AnubisConfigName` | FixedString | 46 (29.7%) | sparse | DefaultMonster / PLA_PersistentFlame / FOR_MeltingFurnace |
| `Archetype` | FixedString | 24 (15.5%) | rare | base / mage / imp_melee |
| `BloodSurfaceType` | FixedString | 15 (9.7%) | rare | SurfaceNone / SurfaceBlood / SurfacePoison |
| `BloodType` | FixedString | 11 (7.1%) | rare | Red / Green |
| `CameraOffset` | fvec3 | 7 (4.5%) | rare | 0 0 0 |
| `CanBePickedUp` | bool | 4 (2.6%) | rare | True / False |
| `CanBeTeleported` | bool | 1 (0.6%) | rare | True |
| `CanClimbLadders` | bool | 3 (1.9%) | rare | False / True |
| `CanFight` | bool | 4 (2.6%) | rare | True / False |
| `CanJoinCombat` | bool | 2 (1.3%) | rare | False |
| `CanOpenDoors` | bool | 1 (0.6%) | rare | False |
| `CharacterVisualResourceID` | FixedString | 139 (89.7%) | very common | 7a7a65c4-7590-e5bf-7cb7-09a8573c73fa / 91fcb6a4-bf5f-2a3c-f538-8924593a644c / f3b06680-b2a2-e8a0-925d-9378bbb08360 |
| `CombatGroupID` | FixedString | 5 (3.2%) | rare | 567b5ad7-687c-ca8f-3763-e21195a99d00 / b8945d7f-7a8d-ab9a-0a47-63b124322028 |
| `CombatName` | LSString | 3 (1.9%) | rare | S_GOB_Goblin_INT_King_01 / S_GOB_Checkpoint_Goblin_Melee_01 / S_FOR_Gnome_Goblin_Melee_01 |
| `CriticalHitType` | FixedString | 2 (1.3%) | rare | Default |
| `DeathEffect` | guid | 7 (4.5%) | rare | 9e156f86-4b68-4d8b-a282-f6ee24dd7819 / eb0aa43b-fcdc-4ef2-8c54-f60e75074e83 / 00000000-0000-0000-0000-000000000000 |
| `DeathRaycastMaxLength` | float | 8 (5.2%) | rare | 1.5 / 1 |
| `DefaultState` | uint8 | 1 (0.6%) | rare | 11 |
| `DevComment` | LSString | 5 (3.2%) | rare | |NPC used to introduce oathbreaker to paladins| / Shouldn't be a stone tablets - referred to as a book in dialog / The Hag's human form (disguised with illusion, so mechanically still a hag) |
| `DisableEquipping` | bool | 6 (3.9%) | rare | True |
| `DisintegratedResourceID` | FixedString | 5 (3.2%) | rare | c201a86a-297f-4d0d-16a3-073c1098767b / a8df0d5a-d171-89d2-fd37-424a7f914ec6 |
| `DisplayName` | TranslatedString | 107 (69%) | common |  |
| `Equipment` | FixedString | 76 (49%) | sparse | EQP_Daisy / EQ_Laezel / EQP_Greatsword |
| `EquipmentRace` | guid | 38 (24.5%) | rare | 00000000-0000-0000-0000-000000000000 / 47c0315c-7dc6-4862-b39b-8bf3a10f8b54 / cf421f4e-107b-4ae6-86aa-090419c624a5 |
| `ExplodedResourceID` | FixedString | 4 (2.6%) | rare | 9b371eaa-2ebe-028e-d577-2202ab7acff1 / a8df0d5a-d171-89d2-fd37-424a7f914ec6 / c201a86a-297f-4d0d-16a3-073c1098767b |
| `Faction` | guid | 59 (38.1%) | sparse | 00000000-0000-0000-0000-000000000000 / cfb709b3-220f-9682-bcfb-6f0d8837462e / e7613afc-2775-22c5-9d37-e07a9bbea429 |
| `Flag` | int32 | 47 (30.3%) | sparse | 0 |
| `FoleyLongResourceID` | FixedString | 5 (3.2%) | rare | 4bb9b3aa-3c20-7f72-542c-62274ab76f3e |
| `FoleyMediumResourceID` | FixedString | 1 (0.6%) | rare | 25c4bf99-7b6e-321c-8aac-e56404796f32 |
| `FoleyShortResourceID` | FixedString | 5 (3.2%) | rare | 2363878c-1578-7bc2-b12e-0ba55be1c025 |
| `GeneratePortrait` | LSString | 40 (25.8%) | sparse | Icon_Quasit / Icon_Origin_Laezel / Icon_Origin_Wyll |
| `GroupID` | uint32 | 7 (4.5%) | rare | 0 / 7064 |
| `HasGameplayValue` | bool | 7 (4.5%) | rare | False |
| `Icon` | FixedString | 136 (87.7%) | very common | 7a7a65c4-7590-e5bf-7cb7-09a8573c73fa-_(Icon_Quasit) / Item_DEN_VoloOperation_ErsatzEye / Item_DEC_Goblins_Camp_CookingPot_A_Poisoned |
| `InventoryType` | uint8 | 3 (1.9%) | rare | 14 / 9 / 11 |
| `IsBoss` | bool | 4 (2.6%) | rare | True |
| `IsEquipmentLootable` | bool | 9 (5.8%) | rare | False / True |
| `IsLootable` | bool | 9 (5.8%) | rare | False / True |
| `LadderAttachOffset` | float | 7 (4.5%) | rare | 0 |
| `LadderAttachSpeed` | float | 1 (0.6%) | rare | 3 |
| `LadderDetachSpeed` | float | 1 (0.6%) | rare | 2.5 |
| `LadderLoopSpeed` | float | 10 (6.5%) | rare | 6 / 3.75 / 3 |
| `LevelName` | FixedString | 155 (100%) | always |  |
| `LevelOverride` | int32 | 19 (12.3%) | rare | -1 / 4 / 0 |
| `LightChannel` | uint8 | 10 (6.5%) | rare | 5 / 0 |
| `LightID` | FixedString | 13 (8.4%) | rare | 71749d1d-9b39-46c3-846d-9f342dc27b36 / 362270fc-bf6b-4603-bb8a-6deebbcca47b / 3faa1c66-5d35-4e87-868e-d124168b660f |
| `MapKey` | FixedString | 155 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Name` | LSString | 155 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `ParentTemplateId` | FixedString | 155 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsOpenTemplate` | FixedString | 7 (4.5%) | rare | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 18 (11.6%) | rare | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `PortraitVisualResourceID` | FixedString | 17 (11%) | rare | 685e521d-a4a8-0199-1064-05840a43d28e / 252f4a0d-d502-0985-52f2-973c38377faa / bae88ae9-0be4-cb47-5a1d-3a25b7bbf5e3 |
| `Race` | guid | 20 (12.9%) | rare | 99c33978-f236-4f5b-a8d8-59aeeaf6140f / b6dccbed-30f3-424b-a181-c4540cf38197 / 02e5c59e-80e7-4176-a289-1d08699583f5 |
| `RagdollTemplate` | FixedString | 1 (0.6%) | rare | f6806630-a618-9b15-2c46-8c99f7428bd8 |
| `ReadinessFlags` | uint32 | 4 (2.6%) | rare | 128 / 132 / 12 |
| `RecieveDecal` | bool | 6 (3.9%) | rare | False / True |
| `Scale` | float | 4 (2.6%) | rare | 1 / 1.45 / 1.1 |
| `SoftBodyCollisionTemplate` | FixedString | 4 (2.6%) | rare | 4350b66a-f56a-4f2a-9c60-b5a56609afa4 / 00000000-0000-0000-0000-000000000000 |
| `SoundAttenuation` | int16 | 2 (1.3%) | rare | -1 / 200 / 40 |
| `SoundInitEvent` | FixedString | 2 (1.3%) | rare | 53a5a5a9-d9e1-8375-28e2-c5958cf15df6 / 084a5647-4331-9c43-9bfe-3bb1d36258f1 |
| `SoundMovementStartEvent` | FixedString | 4 (2.6%) | rare | 588ebb89-e66c-4b69-94c8-ba4ac2cc0eab |
| `SoundMovementStopEvent` | FixedString | 5 (3.2%) | rare | d7d5091b-f262-44f2-6296-0099f0baac88 / 09320763-a194-028f-77e7-44c287937394 |
| `SoundObjectIndex` | uint8 | 2 (1.3%) | rare | 0 |
| `SpellSet` | FixedString | 39 (25.2%) | sparse | CommonSummonActions / CommonPlayerActions / CommonNPCActions |
| `Stats` | FixedString | 72 (46.5%) | sparse | FOR_QuasitSummon / UNI_Volo_ErsatzEye / QUEST_GOB_GoblinBoozeTub_Poisoned |
| `SwarmGroup` | FixedString | 1 (0.6%) | rare | PLA_Newborn_Gnolls |
| `Title` | TranslatedString | 9 (5.8%) | rare |  |
| `Type` | FixedString | 155 (100%) | always | item / character / LevelTemplate |
| `UseOcclusion` | bool | 2 (1.3%) | rare | False |
| `UseSoundClustering` | bool | 2 (1.3%) | rare | False |
| `VFXScale` | float | 1 (0.6%) | rare | 1.05 |
| `VisualTemplate` | FixedString | 22 (14.2%) | rare | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |
| `VocalAlertResourceID` | FixedString | 10 (6.5%) | rare | dd97f11e-97e6-ca62-4927-d451ea908606 / 4d987717-c289-ef72-a31d-1851cb2fe023 / 2ebebd33-596f-edea-a781-24177c129887 |
| `VocalAngryResourceID` | FixedString | 7 (4.5%) | rare | 7ad6c6ed-f48f-4337-140d-eb274efaa5e7 / 650bf105-11ee-fde9-f41d-5dcfda83871d / 95eb4ea2-a766-db0d-cb1d-0ed5a4e1bf3b |
| `VocalAnticipationResourceID` | FixedString | 4 (2.6%) | rare | f978a189-ed06-fdf5-6ec3-4df585c42997 / 00000000-0000-0000-0000-000000000000 / c42a6e98-cb63-e95a-836d-a92f21c491b0 |
| `VocalAttackResourceID` | FixedString | 14 (9%) | rare | f91093dc-9cff-6209-c339-1f989cfeb57c / 40ea1faa-fa18-438c-a7de-e6502fb2e432 / 2453885e-6382-66d8-91a9-f73b8c03c1f5 |
| `VocalAwakeResourceID` | FixedString | 6 (3.9%) | rare | b0456735-95f9-3cd2-f76f-9ad1d3676589 / a8d9d28d-2248-a1c0-93ae-8a0626cfcdda / ed05e7e9-d1a5-95eb-9a80-b83df63072be |
| `VocalBoredResourceID` | FixedString | 7 (4.5%) | rare | 93080f52-6904-df3f-fc08-ef56ea2ce95e / 6e6aca73-3d17-33ec-7a12-0ee713dd839f / 4c7e170d-c456-8c04-cd87-75d8d64e0253 |
| `VocalBuffResourceID` | FixedString | 3 (1.9%) | rare | 2b09134f-ca11-cadc-d13d-1687db994c33 |
| `VocalDeathResourceID` | FixedString | 13 (8.4%) | rare | 0cd61230-6240-7606-abaf-dd5c367e1390 / edfc65a1-a99c-417f-9c88-898bcce0a33e / b586f789-d290-f56a-f7c2-3a8a39f71b53 |
| `VocalDodgeResourceID` | FixedString | 14 (9%) | rare | d78e413e-87b0-e2d7-1fa7-ab49f489d17b / 6f2fd945-10df-4009-badc-bb065ed95fc8 / e92ad90d-7a5a-078c-df05-3b76d36b4625 |
| `VocalEffortsResourceID` | FixedString | 7 (4.5%) | rare | db93489e-d406-4d32-941e-6822c4e6d6d8 / 8b490065-b8c0-653c-be0a-88c2d94e567c / e1187b65-7e87-5c0a-446e-48868b4f994a |
| `VocalExhaustedResourceID` | FixedString | 7 (4.5%) | rare | 02d91176-e12f-29df-3a08-746c765d69a1 / fc26a2a3-4275-6773-218a-e906054cc682 / 4518569a-8be5-a76a-0890-720abb37bb2b |
| `VocalFallResourceID` | FixedString | 10 (6.5%) | rare | d22569e3-ef14-b831-7194-5467412b3f8e / 9acac199-393d-c188-8409-3516c2e29460 |
| `VocalGaspResourceID` | FixedString | 1 (0.6%) | rare | 1896ec0d-e17b-bc47-b994-d77cad0f66b9 |
| `VocalIdle1ResourceID` | FixedString | 2 (1.3%) | rare | fc424747-71f7-4828-84d5-95a1d2eae8ae / 6e39843c-842f-ef81-b6e1-608ed7f07662 |
| `VocalIdle2ResourceID` | FixedString | 2 (1.3%) | rare | 30c50c6f-f98b-8369-d429-b6b678042107 / f240303e-820c-27f3-cc33-f34c9b1e0292 |
| `VocalIdle3ResourceID` | FixedString | 2 (1.3%) | rare | 586f0e98-13e5-e173-2923-0ef3a588eedf / 01b2f23e-b3a2-fa21-c7d4-690cf5c33f7c |
| `VocalInitiativeResourceID` | FixedString | 8 (5.2%) | rare | 03a4c740-2a38-de7a-597c-eade8a143849 / 5452daf7-a301-c8b0-4364-428e2841f7f4 / f5d397ca-1ab6-a4a7-a802-9a9305da6ab5 |
| `VocalLaughterManiacalResourceID` | FixedString | 13 (8.4%) | rare | df225c8c-e5fd-4788-b47c-c33b97ccdc3a |
| `VocalLaughterResourceID` | FixedString | 15 (9.7%) | rare | 2b3255d8-a94d-4ae7-8915-c7236d275543 / 0a2990d7-4b6a-46dc-cab5-b98eb6c8e981 |
| `VocalNoneResourceID` | FixedString | 1 (0.6%) | rare | 2af5ab18-2087-45c6-94a8-a968190d618a |
| `VocalPainResourceID` | FixedString | 14 (9%) | rare | 1477f078-24e7-1295-bca1-fd216b0c253b / 2fdbf6c6-72c6-43a4-8001-0d4b5a74ed52 / af25e1e5-8c5f-c369-a3d4-f88818675815 |
| `VocalRebornResourceID` | FixedString | 2 (1.3%) | rare | d32a7f46-7e67-ab71-e5b9-e313c07ea4ba / 293fa315-95db-60ee-64ea-e111b8d649aa |
| `VocalRecoverResourceID` | FixedString | 7 (4.5%) | rare | c7757a75-4a39-0de2-c186-b924ae8f4236 / 1a1ebc76-0465-ae45-9ab9-1719ae46acb1 |
| `VocalRelaxedResourceID` | FixedString | 9 (5.8%) | rare | 3001e2b0-7803-2244-1fba-b4bf06c02f38 / cbea5af8-dc96-2eb1-b0d1-24f2421b29aa / f7d73a55-e753-ccb5-05c5-6bf71b8f2653 |
| `VocalShoutResourceID` | FixedString | 10 (6.5%) | rare | e6ab04ec-6206-9b30-8124-a4b3e6de11a4 / f178cfbf-8331-d81c-f383-230cff46429c |
| `VocalSnoreResourceID` | FixedString | 8 (5.2%) | rare | 1c3322b0-d250-df48-63a1-c12931b579ca / edfd660d-a788-380a-ac21-b4f77b008a4c / 7a65e103-2dac-7a09-fb82-c6ff18f4d7bc |
| `VocalSpawnResourceID` | FixedString | 7 (4.5%) | rare | d32a7f46-7e67-ab71-e5b9-e313c07ea4ba / f6e2e96e-3820-c546-348a-b26d19246058 / 582c99aa-307e-e008-ccc7-91c87792c3b1 |
| `VocalVictoryResourceID` | FixedString | 14 (9%) | rare | 670ff92e-b91e-44d6-d328-763a656f4db8 / 4733fa3b-43d1-977b-ad32-611e0408d2ad / 51994cfd-7015-7f9d-7222-2a291218b594 |
| `VocalWeakResourceID` | FixedString | 11 (7.1%) | rare | 71e8e323-202e-fe83-fcb3-4d0770739e30 / aac800d0-d1fe-cdd3-84bd-184029dff377 / 377cbb98-e1e4-5521-e0ca-c9bc87c4c922 |

**Child Nodes:**
- `Bounds` (Ã—50)
- `EquipmentTypes` (Ã—10)
- `ExcludeInDifficulty` (Ã—2)
- `FootStepInfos` (Ã—13)
- `GameMaster` (Ã—13)
- `ItemList` (Ã—11)
- `LocomotionParams` (Ã—155)
- `OnDeathActions` (Ã—18)
- `OnlyInDifficulty` (Ã—2)
- `PickingPhysics` (Ã—13)
- `ScriptConfigGlobalParameters` (Ã—6)
- `SkillList` (Ã—29)
- `SpeakerGroupList` (Ã—62)
- `StatusList` (Ã—10)
- `Tags` (Ã—91)
- `TradeTreasures` (Ã—22)
- `Treasures` (Ã—24)

### Type: `CombinedLight` (2 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 2 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `Amount` | float | 2 (100%) | always | 0 / 3000 |
| `Angle` | fvec2 | 2 (100%) | always | 35 45 / 35 60 |
| `CameraOffset` | fvec3 | 2 (100%) | always | 0 0 0 |
| `CastShadow` | bool | 2 (100%) | always | False |
| `Color` | fvec3 | 2 (100%) | always | 1 1 1 / 1 0.9411765 0.8627451 |
| `DirectionLightAttenuationEnd` | float | 2 (100%) | always | 1.5 / 1 / 0 |
| `DirectionLightAttenuationFunction` | uint8 | 2 (100%) | always | 2 |
| `DirectionLightAttenuationSide` | float | 2 (100%) | always | 1.7 / 1 / 0 |
| `DirectionLightAttenuationStart` | float | 2 (100%) | always | 0.2 / 1 / 0 |
| `DirectionLightDimensions` | fvec3 | 2 (100%) | always | 2.5 3.5 3 / 2.8 4 3 / 1 1 1 |
| `Enabled` | bool | 2 (100%) | always | True |
| `Flag` | int32 | 2 (100%) | always | 0 |
| `FlatFalloff` | bool | 2 (100%) | always | False / True |
| `Gain` | float | 2 (100%) | always | 2 / 3.5 / 1 |
| `GameplayCheckLOS` | bool | 2 (100%) | always | False |
| `GameplayDirectionalDimensions` | fvec3 | 2 (100%) | always | 1 1 1 |
| `GameplayEdgeSharpening` | float | 2 (100%) | always | 0 |
| `GameplayIsActive` | bool | 2 (100%) | always | True |
| `GameplayRadius` | float | 2 (100%) | always | 6 |
| `GameplaySpotlightAngle` | float | 2 (100%) | always | 40 |
| `GroupID` | uint32 | 2 (100%) | always | 0 / 7064 |
| `HasGameplayValue` | bool | 2 (100%) | always | False |
| `Intensity` | float | 2 (100%) | always | 2 / 3000 / 3 |
| `IsFlickering` | bool | 2 (100%) | always | False |
| `IsHalfLit` | bool | 2 (100%) | always | False |
| `IsMoving` | bool | 2 (100%) | always | False / True |
| `IsSunlight` | bool | 2 (100%) | always | False |
| `Kelvin` | float | 2 (100%) | always | 6400 / 2800 / 4800 |
| `LevelName` | FixedString | 2 (100%) | always |  |
| `LightChannelFlag` | uint8 | 2 (100%) | always | 191 / 32 |
| `LightCookieResource` | FixedString | 2 (100%) | always |  |
| `LightType` | uint8 | 2 (100%) | always | 2 / 0 |
| `MapKey` | FixedString | 2 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `MovementAmount` | float | 2 (100%) | always | 0 / 0.15 |
| `MovementSpeed` | float | 2 (100%) | always | 0 / 5 |
| `Name` | LSString | 2 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `ParentTemplateId` | FixedString | 2 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsOpenTemplate` | FixedString | 2 (100%) | always | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 2 (100%) | always | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `PreExpose` | bool | 2 (100%) | always | True / False |
| `Radius` | float | 2 (100%) | always | 2 / 6 / 16 |
| `RecieveDecal` | bool | 2 (100%) | always | False / True |
| `ScatteringScale` | float | 2 (100%) | always | 0 / 1 / 3 |
| `Shadow` | bool | 2 (100%) | always | False / True |
| `Speed` | float | 2 (100%) | always | 18 / 0 / 10 |
| `Type` | FixedString | 2 (100%) | always | item / character / LevelTemplate |
| `UseTemperature` | bool | 2 (100%) | always | True / False |
| `VisualTemplate` | FixedString | 2 (100%) | always | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |
| `VolumetricShadow` | bool | 2 (100%) | always | False / True |

### Type: `decal` (5 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 5 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `AngleCutoff` | float | 1 (20%) | rare | 0.8 |
| `CameraOffset` | fvec3 | 5 (100%) | always | 0 0 0 |
| `Dimensions` | fvec3 | 5 (100%) | always | 1 1 1 |
| `Flag` | int32 | 5 (100%) | always | 0 |
| `GroupID` | uint32 | 5 (100%) | always | 0 / 7064 |
| `HasGameplayValue` | bool | 5 (100%) | always | False |
| `Layer` | uint32 | 5 (100%) | always | 0 |
| `LevelName` | FixedString | 5 (100%) | always |  |
| `MapKey` | FixedString | 5 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Material` | FixedString | 5 (100%) | always | 7ea41503-e23f-d7ce-3aec-49d396a74297 / 21ecd5b6-4b42-f191-b148-a2534b18307d / f8bc6b1b-f055-439b-e273-44a6e3ebd90d |
| `Name` | LSString | 5 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `NormalBlendingFactor` | float | 5 (100%) | always | 0 |
| `offset` | fvec2 | 5 (100%) | always | 0 0 |
| `Opacity` | float | 1 (20%) | rare | 0 / 1 |
| `ParentTemplateId` | FixedString | 5 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsOpenTemplate` | FixedString | 1 (20%) | rare | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 5 (100%) | always | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `Tiling` | fvec2 | 5 (100%) | always | 1 1 |
| `Type` | FixedString | 5 (100%) | always | item / character / LevelTemplate |
| `UUID` | FixedString | 4 (80%) | very common |  |
| `VisualTemplate` | FixedString | 5 (100%) | always | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |

### Type: `item` (588 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 588 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `AiHint` | guid | 16 (2.7%) | rare | 00000000-0000-0000-0000-000000000000 / f76e60e1-2957-470b-8a25-efdf32475ce0 / f5614548-32cc-4e2e-b108-32e5d532471e |
| `AllowSummonTeleport` | bool | 1 (0.2%) | rare | True |
| `AnubisConfigName` | FixedString | 13 (2.2%) | rare | DefaultMonster / PLA_PersistentFlame / FOR_MeltingFurnace |
| `Archetype` | FixedString | 16 (2.7%) | rare | base / mage / imp_melee |
| `AttackableWhenClickThrough` | bool | 12 (2%) | rare | False |
| `BloodSurfaceType` | FixedString | 18 (3.1%) | rare | SurfaceNone / SurfaceBlood / SurfacePoison |
| `BookType` | uint8 | 2 (0.3%) | rare | 3 |
| `CameraOffset` | fvec3 | 17 (2.9%) | rare | 0 0 0 |
| `CanBeImprovisedWeapon` | bool | 1 (0.2%) | rare | True |
| `CanBeMoved` | bool | 26 (4.4%) | rare | False / True |
| `CanBePickedUp` | bool | 22 (3.7%) | rare | True / False |
| `CanClickThrough` | bool | 69 (11.7%) | rare | False / True |
| `CanClimbOn` | bool | 93 (15.8%) | rare | False / True |
| `CanFight` | bool | 2 (0.3%) | rare | True / False |
| `CanJoinCombat` | bool | 7 (1.2%) | rare | False |
| `CanShootThrough` | bool | 120 (20.4%) | rare | True / False |
| `CastShadow` | bool | 9 (1.5%) | rare | False |
| `ColorPreset` | guid | 1 (0.2%) | rare | 68d055b3-c3df-ab42-857d-cfe747e4a85b |
| `ConstellationConfigName` | FixedString | 2 (0.3%) | rare | FallingStalactite |
| `CoverAmount` | uint8 | 105 (17.9%) | rare | 0 / 1 |
| `DefaultState` | FixedString | 6 (1%) | rare | open / closed |
| `Description` | TranslatedString | 223 (37.9%) | sparse |  |
| `Destroyed` | bool | 15 (2.6%) | rare | True |
| `DevComment` | LSString | 5 (0.9%) | rare | |NPC used to introduce oathbreaker to paladins| / Shouldn't be a stone tablets - referred to as a book in dialog / The Hag's human form (disguised with illusion, so mechanically still a hag) |
| `DisarmDifficultyClassID` | guid | 2 (0.3%) | rare | 831e1fbe-428d-4f4d-bd17-4206d6efea35 |
| `DisplayName` | TranslatedString | 413 (70.2%) | common |  |
| `DropSound` | FixedString | 19 (3.2%) | rare | fef7023c-75c1-6d74-0668-4e5ab2eb59e4 / 8891f42c-f66e-b87a-d0b7-6f2de68489a8 / 23c6ee88-e1ae-88e5-71d5-b127b60f68ee |
| `EquipmentTypeID` | guid | 13 (2.2%) | rare | 12b80df8-aaf1-4543-84fa-c44622e451b5 / 00000000-0000-0000-0000-000000000000 / 62ff4f7c-0724-43fa-997b-ef0c486a5573 |
| `EquipSound` | FixedString | 6 (1%) | rare | c0c9b3e7-b3bc-2cbc-9de5-0a148cb098cc / 92550df7-e13e-4474-8a7e-a59825eaa805 / 4be7393e-909d-af74-1d02-85caf412cac4 |
| `ExamineRotation` | fvec3 | 9 (1.5%) | rare | 65 180 0 / 75 180 0 / 65 18 0 |
| `Faction` | guid | 28 (4.8%) | rare | 00000000-0000-0000-0000-000000000000 / cfb709b3-220f-9682-bcfb-6f0d8837462e / e7613afc-2775-22c5-9d37-e07a9bbea429 |
| `Fadeable` | bool | 6 (1%) | rare | True |
| `FadeIn` | bool | 1 (0.2%) | rare | True |
| `Flag` | int32 | 83 (14.1%) | rare | 0 |
| `Flag` | uint8 | 1 (0.2%) | rare | 0 |
| `Floating` | bool | 1 (0.2%) | rare | True |
| `FreezeGravity` | bool | 3 (0.5%) | rare | False / True |
| `GravityType` | uint8 | 9 (1.5%) | rare | 1 / 0 |
| `GroupID` | uint32 | 17 (2.9%) | rare | 0 / 7064 |
| `HasGameplayValue` | bool | 17 (2.9%) | rare | False |
| `HierarchyOnlyFade` | bool | 6 (1%) | rare | True |
| `Hostile` | bool | 2 (0.3%) | rare | True |
| `Icon` | FixedString | 303 (51.5%) | common | 7a7a65c4-7590-e5bf-7cb7-09a8573c73fa-_(Icon_Quasit) / Item_DEN_VoloOperation_ErsatzEye / Item_DEC_Goblins_Camp_CookingPot_A_Poisoned |
| `IgnoreGenerics` | bool | 1 (0.2%) | rare | True |
| `ImpactSound` | FixedString | 40 (6.8%) | rare | d44f2631-ebea-49ff-79ba-415636e0270a / 80788119-e116-0b2b-6e33-92d15eaf3bcc / fa6145a3-f95d-60a9-9583-ba601bc3a583 |
| `InteractionFilterType` | uint8 | 3 (0.5%) | rare | 2 |
| `InventoryMoveSound` | FixedString | 17 (2.9%) | rare | fef7023c-75c1-6d74-0668-4e5ab2eb59e4 / 8891f42c-f66e-b87a-d0b7-6f2de68489a8 / 23c6ee88-e1ae-88e5-71d5-b127b60f68ee |
| `InventoryType` | uint8 | 27 (4.6%) | rare | 14 / 9 / 11 |
| `IsBlueprintDisabledByDefault` | bool | 8 (1.4%) | rare | False |
| `IsDecorative` | bool | 1 (0.2%) | rare | True |
| `IsInspector` | bool | 47 (8%) | rare | False / True |
| `IsInteractionDisabled` | bool | 4 (0.7%) | rare | True |
| `IsPlatformOwner` | bool | 2 (0.3%) | rare | True |
| `IsPointerBlocker` | bool | 73 (12.4%) | rare | False |
| `IsPortal` | bool | 14 (2.4%) | rare | False |
| `IsPortalProhibitedToPlayers` | bool | 1 (0.2%) | rare | True |
| `IsPublicDomain` | bool | 2 (0.3%) | rare | True |
| `IsSurfaceBlocker` | bool | 2 (0.3%) | rare | True |
| `IsSurfaceCloudBlocker` | bool | 1 (0.2%) | rare | True |
| `IsTrap` | bool | 1 (0.2%) | rare | True |
| `Key` | FixedString | 1 (0.2%) | rare | UND_SeluneOutpost_Key |
| `LevelName` | FixedString | 588 (100%) | always |  |
| `LevelOverride` | int32 | 33 (5.6%) | rare | -1 / 4 / 0 |
| `LoopSound` | FixedString | 88 (15%) | rare | edab4cf9-5637-fa0e-43fe-49305c5a3218 / 14523ac7-8dbc-4d82-0deb-92ff37d92954 / 92182f4d-e6e8-1022-0ee2-8df5446bf303 |
| `MapKey` | FixedString | 588 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `maxStackAmount` | int32 | 30 (5.1%) | rare | 1 / 100 / 99 |
| `MeshProxy` | FixedString | 17 (2.9%) | rare | 3f38bcda-21ee-66bb-3c6d-be241a1df6f0 |
| `Name` | LSString | 588 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `OnUseDescription` | TranslatedString | 8 (1.4%) | rare |  |
| `Opacity` | float | 10 (1.7%) | rare | 0 / 1 |
| `ParentTemplateId` | FixedString | 588 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsCollisionSound` | FixedString | 1 (0.2%) | rare | 0c130d61-2b03-3abb-2d1d-3ea22eb35034 |
| `PhysicsOpenTemplate` | FixedString | 14 (2.4%) | rare | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 385 (65.5%) | common | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `PickupSound` | FixedString | 21 (3.6%) | rare | c87e342d-a717-4d86-c15a-6c0c7d9520c1 / 0c6e22db-8de7-919a-88c3-79532bca7898 / 06cee190-7109-18f2-8c2e-6eedc1eff4b2 |
| `Race` | int8 | 3 (0.5%) | rare | -1 / 2 |
| `ReadinessFlags` | uint32 | 276 (46.9%) | sparse | 128 / 132 / 12 |
| `RecieveDecal` | bool | 27 (4.6%) | rare | False / True |
| `Scale` | float | 10 (1.7%) | rare | 1 / 1.45 / 1.1 |
| `SeeThrough` | bool | 4 (0.7%) | rare | True |
| `ShootThroughType` | int8 | 11 (1.9%) | rare | 6 / -1 |
| `ShowAttachedSpellDescriptions` | bool | 4 (0.7%) | rare | True |
| `SoundAttenuation` | int16 | 78 (13.3%) | rare | -1 / 200 / 40 |
| `SoundInitEvent` | FixedString | 75 (12.8%) | rare | 53a5a5a9-d9e1-8375-28e2-c5958cf15df6 / 084a5647-4331-9c43-9bfe-3bb1d36258f1 |
| `SpeakerGroup` | LSString | 1 (0.2%) | rare | 69b61817-8458-47ac-8e78-5e855b0999ab |
| `Stats` | FixedString | 310 (52.7%) | common | FOR_QuasitSummon / UNI_Volo_ErsatzEye / QUEST_GOB_GoblinBoozeTub_Poisoned |
| `StoryItem` | bool | 18 (3.1%) | rare | False / True |
| `TechnicalDescription` | TranslatedString | 22 (3.7%) | rare |  |
| `TechnicalDescriptionParams` | LSString | 1 (0.2%) | rare | 2 |
| `TemplateName` | FixedString | 4 (0.7%) | rare |  |
| `Tooltip` | uint8 | 65 (11.1%) | rare | 1 / 2 / 0 |
| `TreasureOnDestroy` | bool | 66 (11.2%) | rare | False / True |
| `Type` | FixedString | 588 (100%) | always | item / character / LevelTemplate |
| `UnequipSound` | FixedString | 4 (0.7%) | rare | f69d46c0-213b-038a-5281-9533b61dca7b / 61e89d62-d151-afb2-5c0f-6420a72debfb |
| `Unimportant` | bool | 3 (0.5%) | rare | True |
| `UnknownDescription` | TranslatedString | 3 (0.5%) | rare |  |
| `UnknownDisplayName` | TranslatedString | 2 (0.3%) | rare |  |
| `UseSound` | FixedString | 7 (1.2%) | rare | 10a8b532-de0b-616e-ffc5-006fcefa8d05 / 817b988e-3cc1-78e6-54bc-45da77580f54 / 434c976d-41d7-3f61-c3fd-f62ffcf2a59e |
| `VisualTemplate` | FixedString | 429 (73%) | common | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |
| `Wadable` | bool | 65 (11.1%) | rare | False / True |
| `WadableSurfaceType` | FixedString | 3 (0.5%) | rare | SurfaceDeepWater |
| `WalkOn` | bool | 71 (12.1%) | rare | False / True |
| `WalkThrough` | bool | 115 (19.6%) | rare | True / False |

**Child Nodes:**
- `AIBounds` (Ã—3)
- `AttachedRoomTriggersList` (Ã—4)
- `Bounds` (Ã—396)
- `ConstellationConfigGlobalParameters` (Ã—8)
- `Equipment` (Ã—71)
- `ExcludeInDifficulty` (Ã—1)
- `FadeChildren` (Ã—6)
- `GameMaster` (Ã—97)
- `InteractionFilterList` (Ã—3)
- `InventoryList` (Ã—84)
- `ItemList` (Ã—17)
- `LayerList` (Ã—9)
- `OnDestroyActions` (Ã—183)
- `OnlyInDifficulty` (Ã—1)
- `OnUsePeaceActions` (Ã—270)
- `ScriptConfigGlobalParameters` (Ã—23)
- `ScriptOverrides` (Ã—25)
- `Scripts` (Ã—71)
- `SpeakerGroupList` (Ã—3)
- `StatusList` (Ã—23)
- `Tags` (Ã—116)

### Type: `LevelTemplate` (113 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 113 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `CameraOffset` | fvec3 | 113 (100%) | always | 0 0 0 |
| `Flag` | int32 | 112 (99.1%) | always | 0 |
| `Flag` | uint8 | 1 (0.9%) | rare | 0 |
| `GroupID` | uint32 | 113 (100%) | always | 0 / 7064 |
| `HasGameplayValue` | bool | 112 (99.1%) | always | False |
| `IsCinematic` | bool | 6 (5.3%) | rare | False |
| `IsDynamicLayer` | bool | 31 (27.4%) | sparse | False |
| `IsMoving` | bool | 58 (51.3%) | common | False / True |
| `IsScrollingObject` | bool | 67 (59.3%) | common | False / True |
| `LevelName` | FixedString | 113 (100%) | always |  |
| `LevelTemplateType` | uint8 | 41 (36.3%) | sparse | 0 / 1 |
| `MapKey` | FixedString | 113 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `MovablePlatformStartSound` | FixedString | 26 (23%) | rare | 9d4f53f9-83bd-8d55-6560-16bf23e21154 / b2802ca6-a2ac-9f2f-927c-c8bfbcb5b00d / 85018e75-1504-9afc-f4b4-fe1a3210d329 |
| `MovablePlatformStopSound` | FixedString | 26 (23%) | rare | 54604628-1d45-5ae0-95e9-ddb97e905137 / 76d64a2f-9f86-70c8-f483-da305eb0f11f / c9917b16-72ed-33da-0a7f-7d079a443887 |
| `Name` | LSString | 113 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `ParentTemplateId` | FixedString | 111 (98.2%) | very common | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `Persistent` | bool | 72 (63.7%) | common | False |
| `PhysicsOpenTemplate` | FixedString | 44 (38.9%) | sparse | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 113 (100%) | always | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `Scale` | float | 9 (8%) | rare | 1 / 1.45 / 1.1 |
| `ScrollingDirection` | fvec3 | 67 (59.3%) | common | 1 0 0 |
| `ScrollingDistance` | float | 67 (59.3%) | common | 0 / 12000 |
| `ScrollingOffset` | float | 64 (56.6%) | common | 0 |
| `ScrollingOrigin` | fvec3 | 56 (49.6%) | sparse | 0 0 0 / 0 -230 0 |
| `ScrollingSpeed` | float | 67 (59.3%) | common | 0 / 200 |
| `SoundActivationRange` | float | 8 (7.1%) | rare | -1 |
| `StartingActive` | bool | 113 (100%) | always | False / True |
| `StartingLoaded` | bool | 68 (60.2%) | common | True |
| `SubLevelName` | FixedString | 113 (100%) | always | PLT_Underdark_TeleportPlatform / WLD_OwlbearCave_B / WLD_DenSubs_B |
| `TemplateAfterDestruction` | FixedString | 84 (74.3%) | common | 10f3bc44-31e2-4bb5-b200-fd9eb9a2c36f / 091931ef-6640-43fa-8772-b656c1c5a539 / 9da1f1a5-de4e-4092-ab0a-1a424a1bbd7e |
| `Type` | FixedString | 113 (100%) | always | item / character / LevelTemplate |
| `UseSoundOcclusion` | bool | 12 (10.6%) | rare | True |
| `VisualTemplate` | FixedString | 113 (100%) | always | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |

**Child Nodes:**
- `ConstellationConfigGlobalParameters` (Ã—15)
- `LayerList` (Ã—45)
- `Tags` (Ã—3)

### Type: `light` (18 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 18 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `Amount` | float | 5 (27.8%) | sparse | 0 / 3000 |
| `Angle` | fvec2 | 15 (83.3%) | very common | 35 45 / 35 60 |
| `CameraOffset` | fvec3 | 4 (22.2%) | rare | 0 0 0 |
| `CastShadow` | bool | 3 (16.7%) | rare | False |
| `Color` | fvec3 | 4 (22.2%) | rare | 1 1 1 / 1 0.9411765 0.8627451 |
| `DirectionLightAttenuationEnd` | float | 14 (77.8%) | very common | 1.5 / 1 / 0 |
| `DirectionLightAttenuationFunction` | uint8 | 4 (22.2%) | rare | 2 |
| `DirectionLightAttenuationSide` | float | 14 (77.8%) | very common | 1.7 / 1 / 0 |
| `DirectionLightAttenuationStart` | float | 14 (77.8%) | very common | 0.2 / 1 / 0 |
| `DirectionLightDimensions` | fvec3 | 13 (72.2%) | common | 2.5 3.5 3 / 2.8 4 3 / 1 1 1 |
| `Enabled` | bool | 4 (22.2%) | rare | True |
| `Flag` | int32 | 4 (22.2%) | rare | 0 |
| `FlatFalloff` | bool | 14 (77.8%) | very common | False / True |
| `Gain` | float | 13 (72.2%) | common | 2 / 3.5 / 1 |
| `GroupID` | uint32 | 4 (22.2%) | rare | 0 / 7064 |
| `HasGameplayValue` | bool | 3 (16.7%) | rare | False |
| `Intensity` | float | 16 (88.9%) | very common | 2 / 3000 / 3 |
| `IsFlickering` | bool | 4 (22.2%) | rare | False |
| `IsMoving` | bool | 4 (22.2%) | rare | False / True |
| `Kelvin` | float | 5 (27.8%) | sparse | 6400 / 2800 / 4800 |
| `LevelName` | FixedString | 18 (100%) | always |  |
| `LightChannelFlag` | uint8 | 4 (22.2%) | rare | 191 / 32 |
| `LightType` | uint8 | 15 (83.3%) | very common | 2 / 0 |
| `LightVolume` | bool | 1 (5.6%) | rare | False |
| `LightVolumeSamplesCount` | int32 | 1 (5.6%) | rare | 1024 |
| `MapKey` | FixedString | 18 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `MovementAmount` | float | 4 (22.2%) | rare | 0 / 0.15 |
| `MovementSpeed` | float | 4 (22.2%) | rare | 0 / 5 |
| `Name` | LSString | 18 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `ParentTemplateId` | FixedString | 18 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsOpenTemplate` | FixedString | 3 (16.7%) | rare | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 4 (22.2%) | rare | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `PreExpose` | bool | 4 (22.2%) | rare | True / False |
| `Radius` | float | 13 (72.2%) | common | 2 / 6 / 16 |
| `RecieveDecal` | bool | 4 (22.2%) | rare | False / True |
| `ScatteringScale` | float | 14 (77.8%) | very common | 0 / 1 / 3 |
| `Shadow` | bool | 4 (22.2%) | rare | False / True |
| `Speed` | float | 4 (22.2%) | rare | 18 / 0 / 10 |
| `TextureMapping` | uint8 | 1 (5.6%) | rare | 0 |
| `Type` | FixedString | 18 (100%) | always | item / character / LevelTemplate |
| `UseTemperature` | bool | 10 (55.6%) | common | True / False |
| `VisualTemplate` | FixedString | 4 (22.2%) | rare | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |
| `VolumetricLightCollisionProbability` | float | 1 (5.6%) | rare | 0.0001 |
| `VolumetricLightIntensity` | float | 1 (5.6%) | rare | 5000 |
| `VolumetricShadow` | bool | 3 (16.7%) | rare | False / True |

### Type: `lightProbe` (1 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 1 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `CameraOffset` | fvec3 | 1 (100%) | always | 0 0 0 |
| `CaptureType` | uint8 | 1 (100%) | always | 2 |
| `CastShadow` | bool | 1 (100%) | always | False |
| `Enabled` | bool | 1 (100%) | always | True |
| `Flag` | int32 | 1 (100%) | always | 0 |
| `GroupID` | uint32 | 1 (100%) | always | 0 / 7064 |
| `HasGameplayValue` | bool | 1 (100%) | always | False |
| `InfiniteCapture` | bool | 1 (100%) | always | True |
| `Intensity` | float | 1 (100%) | always | 2 / 3000 / 3 |
| `LevelName` | FixedString | 1 (100%) | always |  |
| `LightProbeShape` | uint8 | 1 (100%) | always | 0 |
| `LightProbeType` | uint8 | 1 (100%) | always | 1 |
| `MapKey` | FixedString | 1 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Name` | LSString | 1 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `PhysicsTemplate` | FixedString | 1 (100%) | always | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `Radius` | float | 1 (100%) | always | 2 / 6 / 16 |
| `RecieveDecal` | bool | 1 (100%) | always | False / True |
| `Scale` | float | 1 (100%) | always | 1 / 1.45 / 1.1 |
| `Size` | fvec3 | 1 (100%) | always | 10 10 10 |
| `TransitionDistance` | float | 1 (100%) | always | 1 |
| `TriggerAtmosphere` | FixedString | 1 (100%) | always |  |
| `Type` | FixedString | 1 (100%) | always | item / character / LevelTemplate |
| `VisualTemplate` | FixedString | 1 (100%) | always | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |

**Child Nodes:**
- `CaptureDescriptions` (Ã—1)
- `LayerList` (Ã—1)
- `Tags` (Ã—1)

### Type: `prefab` (135 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 135 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `CameraOffset` | fvec3 | 135 (100%) | always | 0 0 0 |
| `Flag` | int32 | 135 (100%) | always | 0 |
| `GroupID` | uint32 | 135 (100%) | always | 0 / 7064 |
| `HasGameplayValue` | bool | 135 (100%) | always | False |
| `LevelName` | FixedString | 135 (100%) | always |  |
| `MapKey` | FixedString | 135 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Name` | LSString | 135 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `ParentTemplateId` | FixedString | 134 (99.3%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsOpenTemplate` | FixedString | 41 (30.4%) | sparse | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 135 (100%) | always | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `Scale` | float | 1 (0.7%) | rare | 1 / 1.45 / 1.1 |
| `Type` | FixedString | 135 (100%) | always | item / character / LevelTemplate |
| `VisualTemplate` | FixedString | 135 (100%) | always | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |

**Child Nodes:**
- `LayerList` (Ã—66)
- `PrefabChildren` (Ã—1)
- `PrefabChildrenGroup` (Ã—134)
- `PrefabChildrenTransformGroup` (Ã—134)
- `PrefabChildrenTransforms` (Ã—1)
- `Tags` (Ã—2)

### Type: `projectile` (12 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 12 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `Acceleration` | float | 4 (33.3%) | sparse | -5 / 0 / 7 |
| `CameraOffset` | fvec3 | 5 (41.7%) | sparse | 0 0 0 |
| `CastBone` | FixedString | 6 (50%) | common | Dummy_CastFX / Cast_FX / Dummy_Root |
| `CastShadow` | bool | 1 (8.3%) | rare | False |
| `DetachBeam` | bool | 1 (8.3%) | rare | True |
| `Flag` | int32 | 5 (41.7%) | sparse | 0 |
| `GroupID` | uint32 | 5 (41.7%) | sparse | 0 / 7064 |
| `HasGameplayValue` | bool | 5 (41.7%) | sparse | False |
| `ImpactFX` | FixedString | 8 (66.7%) | common | VFX_Script_UND_AdamantineForge_Spark_01 / VFX_Projectiles_Force_Trap_Impact_01 / VFX_Projectiles_Nere_PsychicMirror_Explosion_Impact_01 |
| `InitialSpeed` | float | 9 (75%) | very common | 18 / 10 / 30 |
| `LevelName` | FixedString | 10 (83.3%) | very common |  |
| `LifeTime` | float | 1 (8.3%) | rare | 15 |
| `MapKey` | FixedString | 12 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Name` | LSString | 12 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `OffsetMin_Bezier3` | fvec2 | 4 (33.3%) | sparse | 0 1 / 0 10 / 0 1.5 |
| `ParentTemplateId` | FixedString | 12 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PathRepeat` | uint32 | 1 (8.3%) | rare | 2 |
| `PhysicsOpenTemplate` | FixedString | 4 (33.3%) | sparse | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 5 (41.7%) | sparse | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `PreviewPathImpactFX` | FixedString | 4 (33.3%) | sparse | VFX_UI_DestinationBeam_Projectile_01 |
| `PreviewPathMaterial` | FixedString | 4 (33.3%) | sparse | 312a1494-a0e2-c215-cf51-bda58a6b2341 |
| `ProjectilePath` | uint8 | 3 (25%) | sparse | 3 / 0 |
| `RotateImpact` | bool | 6 (50%) | common | False / True |
| `ShiftBMax_Bezier4` | float | 3 (25%) | sparse | 0.25 |
| `ShiftBMin_Bezier4` | float | 3 (25%) | sparse | 0.25 |
| `ShiftMin_Bezier3` | float | 1 (8.3%) | rare | 0.5 |
| `Speed` | float | 4 (33.3%) | sparse | 18 / 0 / 10 |
| `TrailFX` | FixedString | 1 (8.3%) | rare | VFX_Projectiles_UND_SharFort_Turret_01 |
| `TrajectoryType` | uint8 | 6 (50%) | common | 0 |
| `Type` | FixedString | 12 (100%) | always | item / character / LevelTemplate |
| `VelocityMode` | uint8 | 6 (50%) | common | 1 / 0 |
| `VisualTemplate` | FixedString | 5 (41.7%) | sparse | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |

**Child Nodes:**
- `Bounds` (Ã—5)
- `GameMaster` (Ã—1)

### Type: `scenery` (200 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 200 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `CameraOffset` | fvec3 | 6 (3%) | rare | 0 0 0 |
| `CanClickThrough` | bool | 21 (10.5%) | rare | False / True |
| `CanClimbOn` | bool | 85 (42.5%) | sparse | False / True |
| `CanShootThrough` | bool | 34 (17%) | rare | True / False |
| `CastShadow` | bool | 1 (0.5%) | rare | False |
| `CoverAmount` | uint8 | 104 (52%) | common | 0 / 1 |
| `DisplayName` | TranslatedString | 77 (38.5%) | sparse |  |
| `Fadeable` | bool | 4 (2%) | rare | True |
| `Flag` | int32 | 8 (4%) | rare | 0 |
| `GroupID` | uint32 | 6 (3%) | rare | 0 / 7064 |
| `HasGameplayValue` | bool | 6 (3%) | rare | False |
| `HierarchyOnlyFade` | bool | 4 (2%) | rare | True |
| `IsDecorative` | bool | 1 (0.5%) | rare | True |
| `LevelName` | FixedString | 200 (100%) | always |  |
| `LoopSound` | FixedString | 1 (0.5%) | rare | edab4cf9-5637-fa0e-43fe-49305c5a3218 / 14523ac7-8dbc-4d82-0deb-92ff37d92954 / 92182f4d-e6e8-1022-0ee2-8df5446bf303 |
| `MapKey` | FixedString | 200 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Name` | LSString | 200 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `ParentTemplateId` | FixedString | 200 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsOpenTemplate` | FixedString | 8 (4%) | rare | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 200 (100%) | always | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `ReadinessFlags` | uint32 | 9 (4.5%) | rare | 128 / 132 / 12 |
| `RecieveDecal` | bool | 7 (3.5%) | rare | False / True |
| `SeeThrough` | bool | 2 (1%) | rare | True |
| `Type` | FixedString | 200 (100%) | always | item / character / LevelTemplate |
| `VisualTemplate` | FixedString | 199 (99.5%) | always | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |
| `Wadable` | bool | 1 (0.5%) | rare | False / True |
| `WalkOn` | bool | 88 (44%) | sparse | False / True |
| `WalkThrough` | bool | 31 (15.5%) | rare | True / False |

**Child Nodes:**
- `Bounds` (Ã—155)
- `GameMaster` (Ã—31)

### Type: `SplineConstruction` (1 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 1 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `CameraOffset` | fvec3 | 1 (100%) | always | 0 0 0 |
| `Flag` | int32 | 1 (100%) | always | 0 |
| `GroupID` | uint32 | 1 (100%) | always | 0 / 7064 |
| `HasGameplayValue` | bool | 1 (100%) | always | False |
| `LevelName` | FixedString | 1 (100%) | always |  |
| `MapKey` | FixedString | 1 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Name` | LSString | 1 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `ParentTemplateId` | FixedString | 1 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsTemplate` | FixedString | 1 (100%) | always | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `Scale` | float | 1 (100%) | always | 1 / 1.45 / 1.1 |
| `Type` | FixedString | 1 (100%) | always | item / character / LevelTemplate |
| `VisualTemplate` | FixedString | 1 (100%) | always | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |

**Child Nodes:**
- `LayerList` (Ã—1)
- `tiles` (Ã—1)

### Type: `TileConstruction` (18 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 18 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `CameraOffset` | fvec3 | 18 (100%) | always | 0 0 0 |
| `Flag` | int32 | 18 (100%) | always | 0 |
| `GroupID` | uint32 | 18 (100%) | always | 0 / 7064 |
| `HasGameplayValue` | bool | 18 (100%) | always | False |
| `HiddenFromMinimapRendering` | bool | 1 (5.6%) | rare | True |
| `LevelName` | FixedString | 18 (100%) | always |  |
| `MapKey` | FixedString | 18 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Name` | LSString | 18 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `ParentTemplateId` | FixedString | 18 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsOpenTemplate` | FixedString | 16 (88.9%) | very common | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 18 (100%) | always | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `Type` | FixedString | 18 (100%) | always | item / character / LevelTemplate |
| `VisualTemplate` | FixedString | 18 (100%) | always | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |

**Child Nodes:**
- `ConstructionLines` (Ã—17)
- `ConstructionPoints` (Ã—17)
- `ConstructionSpline` (Ã—17)
- `Fillings` (Ã—17)
- `LayerList` (Ã—2)
- `Tags` (Ã—1)
- `tiles` (Ã—18)

### Type: `trigger` (4 nodes)

| Attribute | Type | Count | Frequency | Examples |
|-----------|------|-------|-----------|----------|
| `_OriginalFileVersion_` | int64 | 4 (100%) | always | 144115207403209023 / 144115207403209022 / 144115207403209029 |
| `Border` | float | 1 (25%) | sparse | 0.5 |
| `CameraOffset` | fvec3 | 4 (100%) | always | 0 0 0 |
| `Color4` | fvec4 | 4 (100%) | always | 0.25 0 0 1 |
| `CustomPointTransform` | mat4x4 | 3 (75%) | very common |  1.00  0.00  0.00  0.00 &#xD;&#xA; 0.00  1.00  0.00  0.00 &#xD;&#xA; 0.00  0.00  1.00  0.00 &#xD;&#xA; 0.00  0.00  0.00  1.00 &#xD;&#xA; |
| `Extents` | fvec3 | 4 (100%) | always | 1 1 1 |
| `Fadeable` | bool | 1 (25%) | sparse | True |
| `FadeGroupOnly` | bool | 3 (75%) | very common | False |
| `Flag` | int32 | 4 (100%) | always | 0 |
| `GizmoColorOverride` | fvec4 | 4 (100%) | always | 0 0 0.25 1 / 0.5 0.5 0.5 0.5 |
| `GroupID` | uint32 | 4 (100%) | always | 0 / 7064 |
| `HasCustomPoint` | bool | 4 (100%) | always | False |
| `HasGameplayValue` | bool | 4 (100%) | always | False |
| `IsRooof` | bool | 1 (25%) | sparse | False |
| `LevelName` | FixedString | 4 (100%) | always |  |
| `MapKey` | FixedString | 4 (100%) | always | 000ae223-f71c-4749-ba28-e778f9165181 / 000c1be8-615a-4324-b59d-1f0f5637df36 / 000cfc9f-b973-48e7-a5c8-f2992a47a943 |
| `Name` | LSString | 4 (100%) | always | VFX_Cinematic_PostProcess_Distortion_01 / QUEST_FOR_QuasitSummon / DEN_VoloOperation_ErsatzEye |
| `OneShotTrigger` | bool | 1 (25%) | sparse | False |
| `OnlyCharacterEvents` | bool | 1 (25%) | sparse | False |
| `OnlyOsirisEvents` | bool | 1 (25%) | sparse | False |
| `ParentTemplateId` | FixedString | 4 (100%) | always | 93380b9c-cf4f-413d-99a7-7e2897cdb94e / 229e3dc9-e15a-4cf8-bdfb-721a5b2f5e53 / 3e6aac21-333b-4812-a554-376c2d157ba9 |
| `PhysicsOpenTemplate` | FixedString | 4 (100%) | always | d476ea9e-6d78-76ec-efeb-ea5e5eb09c67 |
| `PhysicsTemplate` | FixedString | 4 (100%) | always | 49449edf-fee1-f573-4de0-87522c4e804a / fd587cf8-db5a-8812-6eb3-fc39617e5230 / 3a8733ce-f388-474a-85fb-b62ae21d9f23 |
| `PhysicsType` | int32 | 4 (100%) | always | 2 |
| `RenderMethod` | uint8 | 2 (50%) | common | 1 |
| `TriggerGizmoOverride` | FixedString | 4 (100%) | always |  |
| `TriggerType` | FixedString | 4 (100%) | always | FloorTrigger / RoomTrigger / PortalTrigger |
| `Type` | FixedString | 4 (100%) | always | item / character / LevelTemplate |
| `UsingGizmoColorOverride` | bool | 4 (100%) | always | False |
| `VisualTemplate` | FixedString | 4 (100%) | always | 496b95c3-5efc-3f4a-177c-e4c3999f7d64 / f525e2b0-7a9e-71bc-f6cc-552de2336b70 / c8498b25-a78d-a4ab-7fa5-b2c7a689170a |

**Child Nodes:**
- `ConstellationConfigGlobalParameters` (Ã—2)
- `CustomPointTransform` (Ã—1)
- `FadeChildren` (Ã—3)
- `ScriptConfigGlobalParameters` (Ã—2)
