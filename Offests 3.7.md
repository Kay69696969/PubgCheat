namespace Offsets
{
 //Main Offets
    uintptr_t GEngine = 0xde24c70; //3.7 ULocalPlayer
 uintptr_t GUObjectArray = 0xdb0dfb0; //3.7 GUObject
    uintptr_t GNativeAndroidApp = 0xBBB3590; //GNative
    uintptr_t CanvasMap = 0xde24c70; //3.7  View Matrix
 uintptr_t GName = 0xd877440; //3.7 Gname
  
 //Offets Fileds
 uintptr_t canvas_map = 0xc0; // 3.7 View Matrix
    uintptr_t UWorld = 0x78; // 3.7
    uintptr_t Ulevel = 0x30; //3.7
    uintptr_t RootComponentt = 0x1b0; //3.7
    uintptr_t RelativeLocation = 0x184; // 3.7
    uintptr_t aactorclass = 0xA0; //3.7
    uintptr_t canvas = 0x9d0; // 3.7
    uintptr_t getUWorldNigga = 0x58; //3.7
    uintptr_t LocalPlayer_Key = 0x108;// 3.7
    uintptr_t bUseEncryptLocalPlayerPtr = 0x80;// 3.7
    uintptr_t EncryptedLocalPlayers = 0x38;// 3.7
    uintptr_t LocalPlayers = 0x48;// 3.7
    uintptr_t gameInstance = 0x220;// 3.7
    uintptr_t localActor = 0x30;// 3.7
    uintptr_t LocalPawn = 0x4b0;// 3.7
    uintptr_t PlayerState = 0x460; //3.60x4b0
    uintptr_t ProcessEventIndex = 0;
}


template<typename T>
inline bool IsInvalidPtr(T ptr) {
#if defined(aarch64)
    return (((uintptr_t)ptr & 0xFFFFFFFFFFFFFF) <= 0x1000000000);
#elif defined(arm)
    return ((uintptr_t)ptr <= 0x10000000);
#else
    return (uintptr_t)ptr <= 0x10000000;
#endif
};

template<typename T>
bool IsValidPtr(T x) {
    return !IsInvalidPtr(x);
};

template<typename T>
inline bool vPtr(T x) {
    return !invPtr(x);
};
