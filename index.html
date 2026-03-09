[3/9, 2:50 PM] Ravi Bhai: using UnityEngine;

public class PlayerMovement : MonoBehaviour {
    public float walkSpeed = 5f;
    public float runSpeed = 10f;
    public float gravity = -9.81f;
    
    CharacterController controller;
    Vector3 velocity;

    void Start() {
        controller = GetComponent<CharacterController>();
    }

    void Update() {
        // दौड़ने के लिए Left Shift का उपयोग
        float currentSpeed = Input.GetKey(KeyCode.LeftShift) ? runSpeed : walkSpeed;

        float x = Input.GetAxis("Horizontal");
        float z = Input.GetAxis("Vertical");

        Vector3 move = transform.right * x + transform.forward * z;
        controller.Move(move * currentSpeed * Time.deltaTime);

        // ग्रेविटी (नीचे गिरना)
        velocity.y += gravity * Time.deltaTime;
        controller.Move(velocity * Time.deltaTime);
    }
}
[3/9, 2:50 PM] Ravi Bhai: using UnityEngine;

public class Shooting : MonoBehaviour {
    public float damage = 10f;
    public float range = 100f;
    public Camera fpsCam;

    void Update() {
        if (Input.GetButtonDown("Fire1")) { // माउस का लेफ्ट क्लिक
            Shoot();
        }
    }

    void Shoot() {
        RaycastHit hit;
        if (Physics.Raycast(fpsCam.transform.position, fpsCam.transform.forward, out hit, range)) {
            Debug.Log("Hit: " + hit.transform.name);
            
            // यहाँ दुश्मन की हेल्थ कम करने का लॉजिक आएगा
            Enemy target = hit.transform.GetComponent<Enemy>();
            if (target != null) {
                target.TakeDamage(damage);
            }
        }
    }
}
[3/9, 2:50 PM] Ravi Bhai: using UnityEngine;

public class ZoneShrink : MonoBehaviour {
    public float shrinkSpeed = 0.1f;
    public Vector3 minSize = new Vector3(5, 10, 5);

    void Update() {
        if (transform.localScale.x > minSize.x) {
            // ज़ोन को धीरे-धीरे छोटा करना
            transform.localScale -= new Vector3(shrinkSpeed, 0, shrinkSpeed) * Time.deltaTime;
        }
    }
}
[3/9, 2:51 PM] Ravi Bhai: using UnityEngine;

public class LootItem : MonoBehaviour {
    public string itemName;
    public int level; // 1, 2, या 3
    public float boostValue; // जैसे आर्मर या एक्स्ट्रा डैमेज

    void OnTriggerEnter(Collider other) {
        if (other.CompareTag("Player")) {
            Debug.Log(itemName + " Level " + level + " उठाया गया!");
            // यहाँ खिलाड़ी की इन्वेंट्री में जोड़ने का कोड आएगा
            Destroy(gameObject); // उठाने के बाद ज़मीन से हटा दें
        }
    }
}
