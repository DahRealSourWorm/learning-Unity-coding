# learning-Unity-New-Inputsystem
New Inputsystem


 public InputAction wasd;
    public InputAction Run;
    public CharacterController controller;
    [Space]
    public int Speed = 10;
    public int RunSpeed = 15;
    [Space]
    public float gravity = -9;
    [Space]
    public GameObject Feet;
    public float FeetDis = 0.4f;
    [Space]
    public LayerMask ground;
    private bool isground = true;

    
    
    private void Start()
    {
        controller = GetComponent<CharacterController>();
    }
    void OnEnable()
    {
        wasd.Enable();
    }

     void OnDisable()
    {
        wasd.Disable();
    }
    void Update()
    {
        isground = Physics.CheckSphere(Feet.transform.position, FeetDis, ground);

        
       

        Vector2 inputVector = wasd.ReadValue<Vector2>();

        controller.Move(inputVector * Time.deltaTime * Speed);

       

    }



}

